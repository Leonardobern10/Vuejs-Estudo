<script setup>
import { ref } from "vue";
import Tarefa from "./components/Tarefa.vue";

// Espaço para receber o nome da nova tarefa
const novaTarefa = ref("");

// Lista de objetos cada qual representando uma tarefa
const tarefas = ref([]);

// Responsável pelo valor atual do filtro
const currentFiltro = ref("");

// Função para adicionar tarefa
const inserirNovaTarefa = () => {
  // Verifica se o texto é em branco se for não faz nada
  if (novaTarefa.value.trim() === "") return;

  // Adiciona o objeto Tarefa na lista {tarefas}
  const data = new Date();
  tarefas.value.push({
    id: crypto.randomUUID(),
    data: data.toLocaleString("pt-BR", {
      weekday: "long",
      year: "numeric",
      month: "long",
      day: "numeric",
    }),
    time: data.toLocaleTimeString(),
    title: novaTarefa.value,
    concluida: false,
  });

  // Define o valor de {novaTarefa} para vazio, resetando
  novaTarefa.value = "";
};

// Função para remover tarefa
const removerTarefa = (id) => {
  tarefas.value = tarefas.value.filter((tarefa) => tarefa.id !== id);
};

const tarefaConcluida = (id) => {
  const tarefa = tarefas.value.find((t) => t.id === id);
  if (tarefa) {
    tarefa.concluida = !tarefa.concluida;
  }
};

const atualizaTitulo = (id) => {
  const novoTitulo = prompt("Insira o novo titulo para a tarefa");

  if (!novoTitulo) return;

  const tarefa = tarefas.value.find((tarefa) => tarefa.id === id);
  if (tarefa) {
    tarefa.title = novoTitulo;
  }
};
</script>

<template>
  <div id="cabecalho-pagina">
    <input
      id="input-nova-tarefa"
      v-model="novaTarefa"
      type="text"
      placeholder="Digite sua tarefa..."
      @keyup.enter="inserirNovaTarefa"
    />
    <button @click="inserirNovaTarefa" id="button-adicionar">Adicionar</button>
  </div>
  <div id="container-todas-tarefas">
    <div>
      <Tarefa
        v-for="tarefa in tarefas"
        :key="tarefa.id"
        :titulo="tarefa.title"
        :id="tarefa.id"
        :concluida="tarefa.concluida"
        :remover="removerTarefa"
        :alternar="tarefaConcluida"
        :atualizar="atualizaTitulo"
      />
    </div>
    <div>{{}}</div>
  </div>
  <p>{{}}</p>
</template>

<style scoped>
#cabecalho-pagina {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  width: 100vw;
  padding: 2rem;
}

#input-nova-tarefa {
  height: 2rem;
  width: 70%;
  padding: 1rem;

  border-radius: 10px;
  border: none;
  background-color: #e7ebff8c;
}

#input-nova-tarefa:focus {
  background-color: #6372bf80;
  color: #e7ebff;
}

#input-nova-tarefa:hover {
  background-color: #6372bf80;
  color: #e7ebff;
}

#button-adicionar {
  height: 2rem;
  width: 6rem;
  padding: 0.5rem;
  margin: 0 1rem;

  border-radius: 10px;
  border: none;
  background-color: #c3ccff;
  font-weight: 500;
}
#button-adicionar:hover {
  cursor: pointer;
  background-color: #6372bf80;
}

#filtro {
  height: 2rem;
  width: 6rem;
  padding: 0.5rem 1rem;
  border-radius: 10px;
  border: none;
  background-color: #c3ccff;
  font-weight: 500;
}

#filtro:hover {
  cursor: pointer;
  background-color: #6372bf80;
}

#container-todas-tarefas {
  padding: 5rem;
  padding: 2rem;
  display: grid;
  grid-template-columns: 5fr 1fr;
}
</style>
