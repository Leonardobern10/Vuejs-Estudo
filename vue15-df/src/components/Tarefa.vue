<script setup>
defineProps(["titulo", "id", "concluida", "remover", "alternar", "atualizar"]);
</script>

<template>
  <div id="style-tarefa">
    <div id="cabecalho-tarefa">
      <h3>{{ titulo }}</h3>
      <div id="container-icons">
        <div class="icons-tarefa" id="lixo" @click="remover(id)"></div>
        <div class="icons-tarefa" id="editar" @click="atualizar(id)"></div>
      </div>
    </div>
    <div id="container-status">
      <input
        type="checkbox"
        name="concluido"
        id="concluido"
        :checked="concluida"
        @change="alternar(id)"
      />
      <p v-if="concluida"><strong>Concluido</strong></p>
    </div>
  </div>
</template>

<style scoped>
#style-tarefa {
  margin: 0 2rem;
  margin-bottom: 2rem;
  padding: 1rem;
  max-width: 60%;
  min-width: 50%;
  height: 8rem;
  border-radius: 15px;

  background-color: #c3ccff;

  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
#cabecalho-tarefa {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}
#container-icons {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}
#lixo {
  content: url("../assets/icons/trash.svg");
}
#editar {
  content: url("../assets/icons/editar.svg");
}
.icons-tarefa {
  padding: 0 0.5rem;
  max-width: 2rem;
  min-width: 1rem;
  height: 3rem;
}
#container-status {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}
#concluido {
  background-color: #6673bf46;
  width: 25px;
  height: 25px;
  border-radius: 8px;
  border: 1px solid #6673bf;
  appearance: none;
}
#concluido:checked::after {
  content: url("../assets/icons/correct.svg");
  font-size: 25px;
  text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
  padding-top: 5px;
}
#concluido:checked {
  background-color: #6673bf;
}
</style>
