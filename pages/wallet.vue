<template>
  <div class=" shadow">
      <ChooseWallet :accessWallet="accessWallet" />
  </div>
</template>

<script>
import ChooseWallet from "../components/partials/choose-wallet";
export default {
    components: {
        ChooseWallet
    },
    data() {
        return {
            accessWallet: null
        }
    },
    mounted() {
        this.accessWallet = this.$route.query.access
    }
};
</script>

<style></style>
