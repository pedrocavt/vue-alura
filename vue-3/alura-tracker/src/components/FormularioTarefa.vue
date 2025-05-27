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
        />
      </div>
      <div class="column">
        <TemporizadorTop />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import TemporizadorTop from './TemporizadorTop.vue';

export default defineComponent({
  name: 'FormularioTarefa',
  components: {
    TemporizadorTop
  }
})
</script>