<template>
  <div>
    <Hero />
    <FeatureAction />
    <Integrate />
    <SupportedDapp />
    <Backed />
    <GetStarted />
  </div>
</template>

<script>
import GetStarted from "../components/partials/get-started";
import SupportedDapp from "../components/partials/supported-dapps";
import Backed from "../components/partials/backed";
import Hero from "../components/partials/hero";
import Integrate from "../components/partials/integrate";
import FeatureAction from "../components/partials/feature-action";

export default {
  name: "IndexPage",
  components: {
    Hero,
    GetStarted,
    SupportedDapp,
    Integrate,
    FeatureAction,
    Backed
  },
};
</script>
