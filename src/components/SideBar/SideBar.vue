<template>
  <header>
    <h1>
      <img src="../../assets/logo.png" alt="vue logo" />
    </h1>
    <button class="button" @click="darkMode">{{ buttonText }}</button>
  </header>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "SideBar",
  emits: ["changeTheme"],
  data() {
    return {
      darkModeActive: false,
    };
  },
  computed: {
    buttonText() {
      if (this.darkModeActive) {
        return "Light mode";
      }
      return "Dark mode";
    },
  },
  methods: {
    darkMode() {
      this.darkModeActive = !this.darkModeActive;
      this.$emit("changeTheme", this.darkModeActive);
    },
  },
});
</script>

<style scoped>
header {
  padding: 1rem;
  background: #000b4b;
  width: 100%;
  height: 100vh;
  text-align: center;
}

@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}
</style>
