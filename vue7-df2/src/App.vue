<script setup>
import { ref } from "vue";
import Tarefa from "./components/Tarefa.vue";

const novaTarefa = ref("");
const tarefas = ref([]);

const adicionarTarefa = () => {
  if (novaTarefa.value.trim() === "") return;

  tarefas.value.push({
    id: Date.now(),
    title: novaTarefa.value,
    concluida: false,
  });

  novaTarefa.value = ""; // Limpa o input após adicionar
};

const removerTarefa = (id) => {
  tarefas.value = tarefas.value.filter((tarefa) => tarefa.id !== id);
};

const alternarConcluida = (id) => {
  const tarefa = tarefas.value.find((t) => t.id === id);
  if (tarefa) tarefa.concluida = !tarefa.concluida;
};
</script>

<template>
  <div class="container">
    <div class="containerAdd">
      <input
        v-model="novaTarefa"
        @keyup.enter="adicionarTarefa"
        placeholder="Digite aqui sua tarefa..."
        type="text"
        class="title-task"
      />
      <button @click="adicionarTarefa" class="button-add-task">
        Adicionar
      </button>
    </div>
  </div>

  <ul class="container-all-tasks">
    <Tarefa
      v-for="tarefa in tarefas"
      :key="tarefa.id"
      :id="tarefa.id"
      :title="tarefa.title"
      :concluida="tarefa.concluida"
      :remover="removerTarefa"
      :alternar="alternarConcluida"
    />
  </ul>
</template>

<style scoped>
.containerAdd {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 80vw;
  height: 5vh;
  margin: 2rem 3rem;
}

.container {
  width: 100%;
  display: flex;
  justify-content: center;
}

.title-task {
  width: 80%;
  height: 90%;
  border-radius: 15px;
  border: none;
  padding: 1rem;
}

.button-add-task {
  width: 20%;
  height: 100%;
  margin: 0 2rem;
  border: none;
  border-radius: 15px;
}

.container-all-tasks {
  display: grid;
  grid-template-columns: 40% 40%;
  justify-content: center;
  gap: 2rem;
}
</style>
