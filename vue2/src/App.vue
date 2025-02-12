<script setup>
import { ref } from 'vue';
import Home from './components/Home.vue';
import Archive from './components/Archive.vue';
import Posts from './components/Posts.vue';

//* variável reativa para armazenar a aba atual
const currentTab = ref('Home');

/* * Mapeamento das abas para os componentes */
const tabs = { Home, Posts, Archive };
</script>

<template>
    <div class="container">
        <!-- Botoes de navegação-->
        <div class="tabs">
            <button
                v-for="(component, tab) in tabs"
                :key="tab"
                :class="['tab-button', { active: currentTab === tab }]"
                @click="currentTab = tab"
            >
                {{ tab }}
            </button>
            <component :is="tabs[currentTab]" class="tab-content"></component>
        </div>
    </div>
</template>

<style>
.container {
    text-align: center;
    font-family: Arial, sans-serif;
}
.tabs {
    margin-bottom: 20px;
}
.tab-button {
    padding: 10px 15px;
    border: 1px solid #ccc;
    cursor: pointer;
    background: #f0f0f0;
    margin: 5px;
}
.tab-button.active {
    background: #3498db;
    color: white;
}
.tab-content {
    border: 1px solid #ccc;
    padding: 20px;
}
</style>
