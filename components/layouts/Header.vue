<template>
  <div>
    <div>
      <coingecko-coin-price-marquee-widget
        coin-ids="bitcoin,eos,ethereum,litecoin,ripple,fantasy-doge,etherzero,dai,tezos,filecoin,eos-pow-coin,iota,neo"
        currency="usd"
        background-color="#ffffff"
        locale="en"
      ></coingecko-coin-price-marquee-widget>
    </div>
    <div class="p-6" style="background: #5e00ff">
      <div class="flex justify-between items-center mx-auto max-w-custom-class">
        <h2 class="text-white font-semibold text-2xl">
          <a href="/"> WalletLink </a>
        </h2>
        <nuxt-link to="/#feature-action">
          <button
            href="https://github.com/walletlink/walletlink"
            class="w-full md:w-auto border-4 border-white rounded-full bg-white text-primary px-4 py-3 transition duration-300 ease-in-out hover:bg-transparent hover:text-white"
          >
            Get started
          </button>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style></style>
