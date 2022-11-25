<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <SideBar />
    </div>
    <div class="column is-three-quarter">
      <FormTracker />
      <div class="list"><Task /></div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import SideBar from "./components/SideBar/SideBar.vue";
import FormTracker from "./components/FormTracker/FormTracker.vue";
import Task from "./components/Task/Task.vue";

export default defineComponent({
  name: "App",
  components: {
    SideBar,
    FormTracker,
    Task,
  },
});
</script>

<style>
.list {
  padding: 1.25rem;
}
</style>
