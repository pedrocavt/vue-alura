<template>
    <section class="is-flex is-align-items-center is-justify-content-space-between">
      <CronometroTop :tempoEmSegundos="tempoEmSegundos"/>
      <BotaoTop @clicado="iniciar" icone="fas fa-play" texto="play" :desabilitado="cronometroRodando" />
      <BotaoTop @clicado="finalizar" icone="fas fa-stop" texto="stop" :desabilitado="!cronometroRodando" />
    </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import CronometroTop from './CronometroTop.vue';
import BotaoTop from './BotaoTop.vue';


export default defineComponent({
  name: 'TemporizadorTop',
  emits: ['temporizadorFinalizado'],
  data() {
    return {
      tempoEmSegundos: 0,
      cronometro: 0,
      cronometroRodando: false
    }
  },
  methods: {
    iniciar() {
        this.cronometroRodando = true;
        this.cronometro = setInterval(() => {
            this.tempoEmSegundos += 1
        }, 1000)
    },
    finalizar() {
        this.cronometroRodando = false;
        clearInterval(this.cronometro); 
        this.$emit('temporizadorFinalizado', this.tempoEmSegundos)
        this.tempoEmSegundos = 0;
    }
  },
  components: {
    CronometroTop,
    BotaoTop
  }
})
</script>