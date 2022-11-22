<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter"></div>
    <SideBar />
    <div class="column is-three-quarter"></div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import SideBar from "./components/SideBar/SideBar.vue";
import Form from "./components/Form/Form.vue";

export default defineComponent({
  name: "App",
  components: {
    SideBar,
    Form,
  },
});
</script>

<style></style>
