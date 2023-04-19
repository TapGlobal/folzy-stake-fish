<template>
  <div class="flex flex-col max-w-screen-2xl mx-auto">
    <Header />
    <Nuxt />
    <!-- <Footer /> -->
  </div>
</template>

<script>
import Header from "../components/layouts/Header";
import Footer from "../components/layouts/Footer";
export default {
  components: {
    Footer,
    Header,
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;700&family=Lato:wght@100;300;400;700;900&display=swap');

body {
  font-family: "Lato", sans-serif;
}

html {
  scroll-behavior: smooth;
}

.max-w-custom-class {
  max-width: 1000px;
  min-width: 320px;
}
</style>
