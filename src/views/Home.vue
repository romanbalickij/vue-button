<template>
  <div>
<!--    <AppButton @click.prevent="clicked" >-->
<!--      Sign in-->
<!--    </AppButton>-->

  <AppLabel forInput="email">
    Enter you email
  </AppLabel>


    <AppInput name="email" v-model="form.email"></AppInput>


    <AppTextarea name="bio" v-model="form.email"></AppTextarea>


    <AppSignInModal></AppSignInModal>

    <a href="#" @click.prevent="openModal">Open Modal</a>


     <AppTabss>
        <AppTab name="Tab one">One tab 1</AppTab>
        <AppTab name="Tab two">Two tab 2</AppTab>
     </AppTabss>
  </div>
</template>

<script>


import AppInput from "@/components/AppInput";
import AppLabel from "@/components/AppLabel";
import AppTextarea from "@/components/AppTextArea";

import AppSignInModal from "@/components/modals/AppSignInModal";

import AppTabss from "@/components/tabs/AppTabss";
import AppTab from  "@/components/tabs/AppTab";
export default {
  name: 'Home',
  components: {
    AppInput,
    AppLabel,
    AppTextarea,
    AppSignInModal,
    AppTabss,
    AppTab

  },
  data() {
    return {

       form: {
         email:'roman@balickij9@gmail.com'
       }


    }
  },

  methods:{
    clicked() {

      console.log('gfgf')
    },
    openModal() {

      this.$modal.show('signin',{ name:'Alex' })
    }
  }
}
</script>
