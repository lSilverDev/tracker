<template>
  <main
    class="columns is-gapless is-multiline"
    :class="{ 'dark-mode': changeTheme }"
  >
    <div class="column is-one-quarter">
      <SideBar @changeTheme="switchTheme" />
    </div>
    <div class="column is-three-quarter content">
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
      changeTheme: false,
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
    switchTheme(changeTheme: boolean) {
      this.changeTheme = changeTheme;
    },
  },
});
</script>

<style>
.list {
  padding: 1.25rem;
}

main {
  --bg--primary: white;
  --text--primary: black;
}

main.dark-mode {
  --bg--primary: rgb(0, 0, 0);
  --text--primary: rgb(255, 255, 255);
}

.content {
  background-color: var(--bg--primary);
}
</style>
