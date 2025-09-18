<script setup>
  const props = defineProps(['tarefas']);
</script>


<template>
    <ul v-if="props.tarefas.length > 0" class="list-group mt-4">
    <li v-for="tarefa in props.tarefas" class="list-group-item">
      <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada" :id="tarefa.titulo" type="checkbox"></input>
      <label :class="{ done: tarefa.finalizada }" class="ms-3" :for="tarefa.titulo">
        {{ tarefa.titulo }}
      </label>
    </li>
  </ul>
  <div v-else class="mt-4">
    <h5>Você não possui tarefas pendentes</h5>
  </div>
</template>

<style scoped>
  .done {
    text-decoration: line-through;
  }
</style>