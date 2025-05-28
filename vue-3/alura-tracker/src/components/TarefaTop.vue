<script lang="ts">
import { defineComponent } from 'vue';
import CronometroTop from './CronometroTop.vue';

export default defineComponent({
    name: "TarefaTop",
    components: {
        CronometroTop
    }
});

</script>

<template>
    <div class="box has-text-weight-bold">
        <div class="columns">
            <div class="column is-">
                Descricao
            </div>
            <div class="column">
                <CronometroTop :tempoEmSegundos="15" />
            </div>
        </div>
    </div>
</template>