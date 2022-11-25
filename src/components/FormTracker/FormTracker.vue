<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form">
        <input type="text" class="input" placeholder="task" />
      </div>
      <div class="column">
        <div
          class="is-flex is-align-items-center is-justify-content-space-between"
        >
          <Stopwatch :timeInSec="timeInSec" />
          <button class="button" @click="start()">
            <span class="icon">
              <i class="fas fa-play"></i>
            </span>
            <span>play</span>
          </button>
          <button class="button" @click="finalize()">
            <span class="icon">
              <i class="fas fa-stop"></i>
            </span>
            <span>stop</span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Stopwatch from "../Stopwatch/Stopwatch.vue";

export default defineComponent({
  name: "FormTracker",
  components: {
    Stopwatch,
  },
  data() {
    return {
      timeInSec: 0,
      timer: 0,
    };
  },
  methods: {
    start() {
      this.timer = setInterval(() => {
        this.timeInSec += 1;
      }, 1000);
    },
    finalize() {
      clearInterval(this.timer);
    },
  },
});
</script>
