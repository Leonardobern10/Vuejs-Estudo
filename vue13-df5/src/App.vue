<script setup>
import { ref } from 'vue';
import Tarefa from './components/Tarefa.vue';

const nomeTarefa = ref('');
const todasTarefas = ref([]);
</script>

<template>
    <div id="cadastro-tarefa">
        <input type="text" id="novo-titulo-tarefa" />
        <button id="botao-adicionar">Adicionar</button>
    </div>
    <div id="lista-tarefa">
        <ul>
            <Tarefa title="Titulo de exemplo para uma tarefa" />
        </ul>
    </div>
</template>

<style scoped>
#cadastro-tarefa {
    width: 100vw;
    border: 2px solid black;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
}
#novo-titulo-tarefa {
    min-width: 60%;
    max-width: 40rem;
    height: 2rem;

    margin: 2rem 2rem;
    padding: 0.5rem;

    border: none;
    border-radius: 15px;
}
#botao-adicionar {
    width: 5rem;
    height: 2rem;

    border: none;
    border-radius: 15px;
    padding: 0.5rem;
}
</style>
