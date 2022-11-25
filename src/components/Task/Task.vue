<template>
  <div class="box has-text-weight-bold">
    <div class="columns">
      <div class="column is-7">{{ task?.desc }}</div>
      <div class="column">
        <Stopwatch :timeInSec="task?.duration" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from "vue";
import ITask from "../interface/ITask";
import Stopwatch from "../Stopwatch/Stopwatch.vue";

export default defineComponent({
  name: "Task",
  components: {
    Stopwatch,
  },
  props: {
    task: {
      type: Object as PropType<ITask>,
      requered: true,
    },
  },
});
</script>

<style scoped>
.box {
  background: rgb(201, 201, 201);
}
</style>
