<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form">
        <input type="text" class="input" placeholder="task" v-model="desc" />
      </div>
      <div class="column"><Timer @stopwatchStopped="taskFinished" /></div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Timer from "../Timer/Timer.vue";

export default defineComponent({
  name: "FormTracker",
  emits: ["saveTask"],
  components: {
    Timer,
  },
  data() {
    return { desc: "" };
  },
  methods: {
    taskFinished(timeExpended: number): void {
      this.$emit("saveTask", {
        duration: timeExpended,
        desc: this.desc,
      });
      this.desc = "";
    },
  },
});
</script>
