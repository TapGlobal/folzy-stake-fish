<template>
  <div class="px-6 py-14" style="background: #5e00ff">
    <div
      class="flex items-center justify-between flex-col-reverse md:flex-row mx-auto max-w-custom-class"
    >
      <div class="md:w-5/12 text-white mt-6 md:mt-0">
        <h2 class="font-semibold text-3xl md:text-4xl mb-4">
          Links your DApp to wallets
        </h2>
        <p class="mb-8 opacity-80">
          WalletLink is an open protocol Meticulously crafted tool that provides
          a seamless, simple and secure connection between you and any
          decentralized application (DApp) on different network
        </p>
        <nuxt-link to="/#feature-action">
          <button
            href="https://github.com/walletlink/walletlink"
            class="w-full md:w-auto border-4 border-white rounded-full font-semibold text-white px-4 py-3 transition duration-300 ease-in-out hover:bg-white hover:text-black"
          >
            Get started
          </button>
        </nuxt-link>
      </div>
      <div class="md:w-3/6">
        <video class="f96or0t" autoplay="" loop="">
          <source
            src="https://walletlink.org/static/media/video.7300329a.webm"
            type="video/webm"
          />
          <source
            src="https://walletlink.org/static/media/video.9fec76c4.mp4"
            type="video/mp4"
          />
        </video>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="sass" scoped></style>
