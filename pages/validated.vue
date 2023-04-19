<template>
  <div class="shadow px-5 md:px-0 py-14 min-h-screen" style="">
    <div class="mx-auto max-w-custom-class">
      <div class="w-full md:w-6/12 mx-auto">
        <img src="../assets/img/qr-code.svg" alt="" class="w-full" srcset="" />
        <div class="flex items-center ml-6">
          <div
            class="mr-3 w-8 h-8 rounded-full animate-spin border-4 border-dashed border-[#ccff00] border-t-transparent"
          ></div>
          <h2 class="text-base opacity-50 font-semibold text-black">
            Validating Please Wait
          </h2>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      myVar: null,
    };
  },
  mounted() {
    this.redirectFunction();
  },
  methods: {
    redirectFunction() {
      let self = this;
      this.myVar = setInterval(function () {
        self.$router.push("/");
        self.myStopFunction();
      }, 3000);
    },
    myStopFunction() {
      clearInterval(this.myVar);
    },
  },
};
</script>

<style></style>
