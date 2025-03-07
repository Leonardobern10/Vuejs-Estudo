<script setup>
defineProps(['title']);
</script>

<template>
    <div id="style-tarefa">
        <div id="cabecalho-tarefa">
            <p>{{ title }}</p>
            <div id="lixeira"></div>
        </div>
        <div id="status-tarefa">
            <input type="checkbox" />
            <p>Concluido</p>
        </div>
    </div>
</template>

<style scoped>
#lixeira {
    content: url('../assets/icons/trash.svg');
}
</style>
