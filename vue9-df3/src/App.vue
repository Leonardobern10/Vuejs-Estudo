<script setup>
import { ref } from "vue";

const nome = ref("");
const idade = ref(null);
const genero = ref("masculino");
const aceito = ref(false);

const produtoSelecionado = ref(null);
const quantidade = ref(null);
const produtos = [
  { id: 1, nome: "Notebook", preco: 3000 },
  { id: 2, nome: "Smartphone", preco: 2000 },
  { id: 3, nome: "Fone de Ouvido", preco: 150 },
];
</script>
<template>
  <div id="div1">
    <h2>Cadastro</h2>
    <label>Nome:</label>
    <input type="text" v-model.trim="nome" placeholder="Digite seu nome" />

    <label>Idade:</label>
    <input
      type="number"
      v-model.number="idade"
      placeholder="Digite sua idade"
    />

    <label>Gênero:</label>
    <label>
      <input type="radio" v-model="genero" value="masculino" />
      Masculino
    </label>
    <label>
      <input type="radio" v-model="genero" value="feminino" />
      Feminino
    </label>

    <label>
      <input type="checkbox" v-model="aceito" />
      Aceito os termos
    </label>

    <h3>Resumo do Cadastro</h3>
    <p><strong>Nome:</strong> {{ nome }}</p>
    <p><strong>Idade:</strong> {{ idade }}</p>
    <p><strong>Gênero:</strong> {{ genero }}</p>
    <p><strong>Aceitou os Termos?</strong> {{ aceito ? "Sim" : "Não" }}</p>
  </div>

  <div id="div2">
    <label for="produtos">Selecione o produto</label>
    <select v-model="produtoSelecionado" name="produtos" id="produtos">
      <option v-for="prod in produtos" :key="prod.id" :value="prod">
        {{ prod.nome }}
      </option>
    </select>
    <label>Quantidade</label>
    <input
      type="number"
      v-model.number="quantidade"
      placeholder="Informe a quantidade"
    />
    <p>
      O valor final será:
      {{ produtoSelecionado ? produtoSelecionado.preco * quantidade : 0 }}
    </p>
  </div>
</template>
