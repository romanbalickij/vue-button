<template>
  <div>
    <AppButton @click.prevent="clicked"></AppButton>
  </div>
</template>

<script>

import AppButton from "@/components/AppButton";
export default {
  name: 'Home',
  components: {
    AppButton

  },
  data() {
    return {

        counter: 0

    }
  },

  methods:{
    clicked() {

      console.log('gfgf')
    }
  }
}
</script>
