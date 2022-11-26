<template>
  <section>
    <strong class="stopwatch">{{ elapsedTime }}</strong>
  </section>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Stopwatch",
  props: { timeInSec: { type: Number, default: 0 } },
  computed: {
    elapsedTime(): string {
      return new Date(this.timeInSec * 1000).toISOString().substr(11, 8);
    },
  },
});
</script>

<style>
.stopwatch {
  color: var(--text--primary);
  background-color: var(--bg-primary);
}
</style>
