<template>
    <textarea
        :name="name"
        :id="name"
        :value="value"
        :rows="rows"
        class="form-control"
        @input="$emit('input', $event.target.value)"
    >
    </textarea>
</template>

<script>
export default {

  name: "AppInput",

  props :{

    name:{
      required:true,
      type:String,

    },
    value:{
      required:false,
      type:String,
      default: ''

    },
  },

  computed:{
    rows() {
       return this.value.split("\n").length;
    }
  }



}
</script>

<style scoped>

</style>