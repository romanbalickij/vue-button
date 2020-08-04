<template>
  <transition name="modal">
    <div v-if="visible">
      <div class="app-modal" @click.prevent="visible = false">
        <div class="app-modal-inner">
          <a href="#" @click.prevent="visible = false">X</a>
          <slot :params="params"/>
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
export default {

  name: "AppModal",

  props:{
    name:{
      required:true,
      type:String,

    }
  },

  data() {
    return {
      params:{},
      visible:false
    }
  },

  mounted() {
     this.$modal.$event.$on('show', (modal, params) => {

       if(this.name === modal) {
         this.params  = params
          this.visible = true
       }
     })
  }
}
</script>

<style scoped>
 .app-modal {
   background-color: black ;
   position: fixed;
   width: 100%;
   height:100%;
   top:0;
   left:0;
   z-index: 9999;
 }

 .app-modal-inner {
    position: fixed;
    top:50%;
    left: 50%;
    transform: translate(-50% ,-50%);
    background-color: white ;
    padding: 30px;
    width: 90%;
    max-width: 500px;
 }

 .modal-enter-active, .modal-leave-active {
    transition: all 200ms;
 }

 .modal-enter, .modal-leave-active {
    opacity: 0;
 }
</style>