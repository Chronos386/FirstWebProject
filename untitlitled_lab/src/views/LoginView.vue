<template>
  <section>
    <LoginBlock v-if="sign_in_val"/>
    <AccBlock v-else/>
  </section>
</template>

<script>
import VueCookies from "vue-cookie";
import AccBlock from "@/components/Login/AccBlock";
import LoginBlock from "@/components/Login/LoginBlock";
export default {
  name: "LoginView",
  components: {
    AccBlock,
    LoginBlock
  },
  data() {
    return {
      sign_in_val: VueCookies.get("api_key") === null
    }
  },
  async created() {
    VueCookies.delete('prod_id')
  }
}
</script>