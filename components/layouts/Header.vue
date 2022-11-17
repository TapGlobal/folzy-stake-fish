<template>
  <div>
    <div>
      <!-- <coingecko-coin-price-marquee-widget
        coin-ids="bitcoin,eos,ethereum,litecoin,ripple,fantasy-doge,etherzero,dai,tezos,filecoin,eos-pow-coin,iota,neo"
        currency="usd"
        background-color="#ffffff"
        locale="en"
      ></coingecko-coin-price-marquee-widget> -->
      <coingecko-coin-price-marquee-widget  coin-ids="bitcoin,ethereum,eos,ripple,litecoin" currency="usd" background-color="#ffffff" locale="en"></coingecko-coin-price-marquee-widget>
    </div>
    <div class="p-6" style="background: #184f90">
      <div class="flex justify-between items-center mx-auto max-w-custom-class">
        <h2 class="text-white font-semibold text-2xl">
          <a href="/"> WalletLink </a>
        </h2>
        <nuxt-link to="/access-wallet">
          <button
            class="w-full md:w-auto border-4 border-white rounded-full bg-white text-primary px-4 py-3 transition duration-300 ease-in-out hover:bg-transparent hover:text-white"
          >
            Access my wallet
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
