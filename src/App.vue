<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <SideBar />
    </div>
    <div class="column is-three-quarter">
      <FormTracker />
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import SideBar from "./components/SideBar/SideBar.vue";
import FormTracker from "./components/FormTracker/FormTracker.vue";

export default defineComponent({
  name: "App",
  components: {
    SideBar,
    FormTracker,
  },
});
</script>

<style></style>
