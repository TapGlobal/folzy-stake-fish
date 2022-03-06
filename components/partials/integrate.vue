<template>
  <div class="px-6 py-14" style="background: #262626">
    <div class="flex justify-between items-center flex-col-reverse md:flex-row mx-auto max-w-custom-class">
      <div class="md:w-5/12 mt-10 md:mt-0">
        <img src="../../assets/img/precode.png" alt="" srcset="" />
      </div>
      <div class="text-white md:w-3/6">
        <h2 class="text-2xl mb-4 font-semibold">5 minutes to integrate</h2>
        <p class="mb-7 opacity-80">
          No server deployments, no new library to learn. To integrate with
          WalletLink, all you need to do is drop these few lines to initialize a
          web3 object. WalletLink takes care of the rest. WalletLink is
          open-source and uses minimal dependencies for maximum security and no
          code bloat.
        </p>
        <nuxt-link to="/">
          <button
            href="https://github.com/walletlink/walletlink"
            class="w-full md:w-auto border-4 border-white rounded-full font-semibold text-white px-4 py-3 transition duration-300 ease-in-out hover:bg-white hover:text-black"
          >
            See WalletLink on GitHub
          </button>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="sass" scoped></style>
