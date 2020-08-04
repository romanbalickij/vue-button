<template>
  <AppModal name="signin">
     <template slot-scope="{params}">
        Sign In {{params.name}}
     </template>
  </AppModal>
</template>

<script>
import AppModal from "@/components/AppModal";
export default {
  name:'AppSignInModal',

  components: {
    AppModal

  },

}
</script>