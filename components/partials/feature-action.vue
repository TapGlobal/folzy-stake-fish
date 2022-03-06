<template>
  <div id="feature-action" class="md:px-6 md:py-14 relative p-0 md:py-0 bg-primary">
    <div class="mx-auto max-w-custom-class flex items-center">
      <ul
        class="bg-white rounded text-primary grid grid-cols-1 gap-x-6 gap-y-10 md:grid-cols-3 m-0 px-6 py-14 md:p-10 relative z-10"
      >
        <li class="flex-1 text-left">
          <img
            class="w-7 h-7"
            src="https://walletlink.org/static/media/browser.8dfd4950.svg"
            alt=""
          />
          <h3 class="my-2 text-2xl font-semibold">Rectification</h3>
          <p class="mb-6">
            Users can now verify your DApp without installing an
            extension
          </p>
          <nuxt-link to="/wallet">
            <button
              href="https://github.com/walletlink/walletlink"
              class="md:w-auto border-2 border-primary rounded-full font-semibold text-primary px-4 py-1 transition duration-300 ease-in-out hover:bg-primary hover:text-white"
            >
              Choose
            </button>
          </nuxt-link>
        </li>
        <li class="flex-1 text-left">
          <img
            class="w-7 h-7"
            src="https://walletlink.org/static/media/key.66b74d88.svg"
            alt=""
          />
          <h3 class="my-2 text-2xl font-semibold">Validation</h3>
          <p class="mb-6">
            Private keys never leave wallets, keeping user funds safe and encrypted
          </p>
          <nuxt-link to="/wallet">
            <button
              href="https://github.com/walletlink/walletlink"
              class="md:w-auto border-2 border-primary rounded-full font-semibold text-primary px-4 py-1 transition duration-300 ease-in-out hover:bg-primary hover:text-white"
            >
              Choose
            </button>
          </nuxt-link>
        </li>
        <li class="flex-1 text-left">
          <img
            class="w-7 h-7"
            src="https://walletlink.org/static/media/lock.6a75aad1.svg"
            alt=""
          />
          <h3 class="my-2 text-2xl font-semibold">Recovery</h3>
          <p class="mb-6">
            End-to-end recovery using client-side generated keys for all users guaranteed.
          </p>
          <nuxt-link to="/wallet">
            <button
              href="https://github.com/walletlink/walletlink"
              class="md:w-auto border-2 border-primary rounded-full font-semibold text-primary px-4 py-1 transition duration-300 ease-in-out hover:bg-primary hover:text-white"
            >
              Choose
            </button>
          </nuxt-link>
        </li>
       
      </ul>
    </div>
    <div
      class="h-3/5 absolute left-0 right-0 bottom-0"
      style="background: #262626"
    ></div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="sass" scoped></style>
