<template>
  <div class="is-flex is-align-items-center is-justify-content-space-between">
    <Stopwatch :timeInSec="timeInSec" />
    <button class="button" @click="start()" :disabled="running">
      <span class="icon">
        <i class="fas fa-play"></i>
      </span>
      <span>play</span>
    </button>
    <button class="button" @click="finalize()" :disabled="!running">
      <span class="icon">
        <i class="fas fa-stop"></i>
      </span>
      <span>stop</span>
    </button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Stopwatch from "../Stopwatch/Stopwatch.vue";

export default defineComponent({
  name: "Timer",
  components: {
    Stopwatch,
  },
  data() {
    return {
      timeInSec: 0,
      timer: 0,
      running: false,
    };
  },
  methods: {
    start() {
      this.running = true;
      this.timer = setInterval(() => {
        this.timeInSec += 1;
      }, 1000);
    },
    finalize() {
      this.running = false;
      clearInterval(this.timer);
    },
  },
});
</script>
