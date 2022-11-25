<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <SideBar />
    </div>
    <div class="column is-three-quarter">
      <FormTracker @saveTask="saveTask" />
      <div class="list">
        <Task v-for="(task, index) in tasks" :key="index" :task="task" />
        <Box v-if="emptyList">Nothing to do!</Box>
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import SideBar from "./components/SideBar/SideBar.vue";
import FormTracker from "./components/FormTracker/FormTracker.vue";
import Task from "./components/Task/Task.vue";
import Box from "./components/Box/Box.vue";
import ITask from "./interface/ITask";

export default defineComponent({
  name: "App",
  components: {
    SideBar,
    FormTracker,
    Task,
    Box,
  },
  data() {
    return {
      tasks: [] as ITask[],
    };
  },
  computed: {
    emptyList(): boolean {
      return this.tasks.length === 0;
    },
  },
  methods: {
    saveTask(task: ITask) {
      this.tasks.push(task);
    },
  },
});
</script>

<style>
.list {
  padding: 1.25rem;
}
</style>
