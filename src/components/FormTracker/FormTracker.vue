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
          <section>
            <strong>{{ tempoEmSegundos }}</strong>
          </section>
          <button class="button" @click="iniciar()">
            <span class="icon">
              <i class="fas fa-play"></i>
            </span>
            <span>play</span>
          </button>
          <button class="button" @click="finalizar()">
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

export default defineComponent({
  name: "FormTracker",
  data() {
    return {
      tempoEmSegundos: 0,
    };
  },
  methods: {
    iniciar() {
      setInterval(() => {
        this.tempoEmSegundos += 1;
      }, 1000);
    },
    finalizar() {
      console.log("Finalizar");
    },
  },
});
</script>
