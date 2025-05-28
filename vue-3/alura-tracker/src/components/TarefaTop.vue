<script lang="ts">
import { defineComponent, PropType } from 'vue';
import CronometroTop from './CronometroTop.vue';
import ITarefa from '../interfaces/ITarefa';

export default defineComponent({
    name: "TarefaTop",
    components: {
        CronometroTop
    },
    props: {
        tarefa: {
            type: Object as PropType<ITarefa>,
            required: true
        }
    }
});

</script>

<template>
    <div class="box has-text-weight-bold">
        <div class="columns">
            <div class="column is-">
                {{tarefa.descricao}}
            </div>
            <div class="column">
                <CronometroTop :tempoEmSegundos="tarefa.duracaoEmSegundos" />
            </div>
        </div>
    </div>
</template>