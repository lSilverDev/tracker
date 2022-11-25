<template>
  <div class="box has-text-weight-bold">
    <div class="columns">
      <div class="column is-7">task description</div>
      <div class="column"><Timer :timeInSec="15" /></div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Timer from "../Timer/Timer.vue";

export default defineComponent({
  name: "Task",
  components: {
    Timer,
  },
});
</script>

<style scoped>
.box {
  background: rgb(201, 201, 201);
}
</style>
