<template>
  <div class="px-6 pt-10 pb-40 " style="background: #184f90;">

    <div class="flex justify-between items-left relative mx-auto max-w-custom-class">
        <div class="flex items-center justify-center w-full">
            <div>
                <h1 class="text-3xl font-bold text-center text-white">Access Wallet</h1>
                <p class="text-center text-white">Please select a method to access your wallet.</p>

                <div class="mt-14 md:mt-20 space-y-5 md:space-y-10">
                    <div @click="selectedWallet('mobile')" class="flex justify-between items-center hover:bg-gray-200 cursor-pointer bg-white rounded-xl p-8 md:p-10">
                        <img class="w-1/5 mr-3" src="../assets/img/mobile.png" alt="">
                        <div class="w-4/5">
                            <h2 class="text-xl md:text-2xl mb-3 font-bold">Mobile App Wallet</h2>
                            <p class="text-cente"> MetaMask, TrustWallet, Atomic Wallet, etc </p>
                        </div>
                    </div>
                    <div @click="selectedWallet('hardware')" class="flex justify-between items-center hover:bg-gray-200 cursor-pointer bg-white rounded-xl p-8 md:p-10">
                        <img class="w-1/5 mr-3" src="../assets/img/hardware.png" alt="">
                        <div class="w-4/5">
                            <h2 class="text-xl md:text-2xl mb-3 font-bold">Hardware Wallet</h2>
                            <p class="text-cente"> Ledger, Trezor, KeepKey, Cool Wallet, Bitbox02 </p>
                        </div>
                    </div>
                    <div @click="selectedSoftware" class="flex justify-between items-center hover:bg-gray-200 cursor-pointer bg-white rounded-xl p-8 md:p-10">
                        <img class="w-1/5 mr-3" src="../assets/img/software.png" alt="">
                        <div class="w-4/5">
                            <h2 class="text-xl md:text-2xl mb-3 font-bold">Software</h2>
                            <p class="text-cente">  Keystore File, Mnemonic Phrase, and Private Key  </p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    
  </div>
</template>

<script>
export default {
    methods: {
        selectedSoftware() {
            this.$router.push('/encryption-link')
        },
        selectedWallet(params) {
            this.$router.push(`/wallet?access=${params}`)
        },
    }
}
</script>

<style>

</style>