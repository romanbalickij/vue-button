<template>
  <div>
    <ul class="app-tabs">
      <li v-for="(tab, index) in tabs" :key="index">
        <a href="#" class="app-tab" @click.prevent="switchTab(tab.hash)">
          {{tab.name}}
        </a>
      </li>
    </ul>
    <slot/>
  </div>
</template>

<script>
export default {
  name: "AppTabss",

  data() {
    return {
        tabs:[],
    }
  },

  created() {
    this.tabs =this.$children
  },
  methods:{
     findTab(hash) {
        return this.tabs.find((tab) => {
          return tab.hash === hash
        })
     },

    switchTab(hash) {
      const  selectedTab = this.findTab(hash);

      if(typeof selectedTab === 'undefined') {
        return
      }

        this.tabs.forEach((tab) => {
            tab.active =  (tab.hash === selectedTab.hash)
        })
    }
  },

  mounted() {

    this.switchTab(this.tabs[0].hash)
  }


}
</script>

<style scoped>
.app-tabs {
  display: flex;
  align-items: flex-end;
  border-bottom: 1px solid #eee;
  list-style-type: none;
  padding: 0;
  margin: 0;
}

.app-tab{
  display: block;
  padding: 20px;
  font-weight: bold;
  border-bottom: 3px solid transparent;
  transform: translate(3px);
}
</style>