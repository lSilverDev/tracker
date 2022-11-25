<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form">
        <input type="text" class="input" placeholder="task" />
      </div>
      <div class="column"><Timer /></div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Timer from "../Timer/Timer.vue";

export default defineComponent({
  name: "FormTracker",
  components: {
    Timer,
  },
});
</script>
