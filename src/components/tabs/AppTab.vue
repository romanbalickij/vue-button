<template>
  <div v-show="active" :id="hash">
      <slot/>
  </div>
</template>

<script>
export default {
  name: "AppTab",

  data() {
    return {
      active:false
    }
  },

  computed:{
    hash() {
      return `${this.name.toLowerCase().replace(/ /g,'-')}`
    }
  },

  props:{
    name:{
      required:true,
      type:String,

    }
  }


}
</script>

<style scoped>

</style>