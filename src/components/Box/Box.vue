<template>
  <div class="box has-text-weight-bold"><slot></slot></div>
</template>

<script lang="ts">
import { defineComponent, DefineComponent } from "vue";

export default defineComponent({
  name: "Box",
});
</script>

<style scoped>
.box {
  background: rgb(201, 201, 201);
}
</style>
