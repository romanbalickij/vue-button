<template>
  <label :for="forInput">

    <slot/>

  </label>
</template>

<script>
export default {
  name: "AppLabel",

  props:{
    forInput:{
        required:true,
        type:String,

    }
  }
}
</script>

<style scoped>

</style>