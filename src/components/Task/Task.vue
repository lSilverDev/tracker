<template>
  <Box>
    <div class="columns">
      <div class="column is-7">{{ task?.desc || "without description" }}</div>
      <div class="column">
        <Stopwatch :timeInSec="task?.duration" />
      </div>
    </div>
  </Box>
</template>

<script lang="ts">
import { defineComponent, PropType } from "vue";
import ITask from "../../interface/ITask";
import Stopwatch from "../Stopwatch/Stopwatch.vue";
import Box from "../Box/Box.vue";

export default defineComponent({
  name: "Task",
  components: {
    Stopwatch,
    Box,
  },
  props: {
    task: {
      type: Object as PropType<ITask>,
      requered: true,
    },
  },
});
</script>
