<template>
    <div>
    <input
        :type="inputType"
        :name="name"
        :id="name"
        :value="value"
        class="form-control"
        @input="$emit('input', $event.target.value)"
    >

      <a href="#" v-if="type == 'password'" @click.prevent="passwordRevealed = !passwordRevealed">Reveal password</a>
    </div>


</template>

<script>
export default {

  data() {
    return {
      passwordRevealed:false,

    }
  },
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
    type:{
      required:false,
      type:String,
      default:'text'

    }
  },

  computed:{
    inputType() {

      return this.passwordRevealed ? 'text' : this.type
    }
  },

  methods:{
    toggleVisibility() {

      this.inputType = this.inputType === 'password' ? 'text' : 'password';
    }
  },

  mounted() {
    console.log(this.value)
  }



}
</script>

<style scoped>

</style>