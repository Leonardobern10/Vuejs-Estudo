<script setup>
defineProps(["title", "id", "concluida", "remover", "alternar"]);
</script>

<template>
  <div class="task">
    <div class="container-task">
      <p
        class="title"
        :style="{ textDecoration: concluida ? 'line-through' : 'none' }"
      >
        {{ title }}
      </p>
      <div class="icon-del" @click="remover(id)"></div>
    </div>
    <div class="container-status">
      <input
        type="checkbox"
        class="concluded"
        :checked="concluida"
        @change="alternar(id)"
      />
      <p class="tag-concluded" v-if="concluida">Concluído</p>
    </div>
  </div>
</template>

<style scoped>
.container-task {
  width: 100%;
  min-height: 40%;
  max-height: 80%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.task {
  background-color: #d9d9d9;
  min-height: 8rem;
  max-height: 15rem;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  border-radius: 15px;
  margin-bottom: 1rem;
}

.container-status {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}

.concluded {
  margin-left: 1.5rem;
  width: 1.5rem;
  height: 1.5rem;
}

.tag-concluded {
  margin-right: 1.5rem;
}

.title {
  margin-left: 1.5rem;
  max-width: 80%;
  text-align: start;
}

.icon-del {
  content: url("../assets/icons/trash.svg");
  width: 1.5rem;
  height: 1.5rem;
  cursor: pointer;

  margin-right: 1.5rem;
}
</style>
