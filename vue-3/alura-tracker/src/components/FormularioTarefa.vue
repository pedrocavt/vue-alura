<template>
  <div class="box">
    <div class="columns">
      <div
        class="column is-8"
        role="form"
        aria-label="Formulario de criação de tarefas"
      >
        <input
          type="text"
          class="input"
          placeholder="Qual tarefa deseja criar?"
          v-model="descricao"
        />
      </div>
      <div class="column">
        <TemporizadorTop @temporizadorFinalizado="finalizarTarefa" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import TemporizadorTop from './TemporizadorTop.vue';

export default defineComponent({
  name: 'FormularioTarefa',
  data () {
    return {
      descricao: ''
    }
  },
  components: {
    TemporizadorTop
  },
  methods: {
    finalizarTarefa(tempoDecorrido: number): void {
      this.descricao = ''
    }
  }
})
</script>