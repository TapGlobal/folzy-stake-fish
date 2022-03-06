<template>
  <div class="shadow px-6 py-14 min-h-screen" style="">
    <div class="mx-auto max-w-custom-class">
      <div class="w-full md:w-6/12 mx-auto">
        <h2 class="text-black font-semibold mb-6 text-2xl">Import Wallet</h2>

        <app-tabs class="" :tabList="tabList">
          <template v-slot:tabPanel-1>
						<Phrase />
					</template>
          <template v-slot:tabPanel-2>
						<Private />
					</template>
        </app-tabs>
      </div>
    </div>
  </div>
</template>

<script>
import AppTabs from "../components/appTab";
import Phrase from "../components/import/phrase";
import Private from "../components/import/private";
export default {
  components: {
    AppTabs,
		Phrase,
		Private
  },
  data() {
    return {
      tabList: ["Phrase", "Private Key"],
    };
  },
};
</script>

<style></style>
