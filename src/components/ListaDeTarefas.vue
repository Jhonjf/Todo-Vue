<script setup>
const props = defineProps(['tarefas']);
</script>

<template>
    <ul class="list-group mt-4">
        <li class="list-group-item" v-for="tarefa in props.tarefas" :key="tarefa.titulo">
            <input type="checkbox" :id="tarefa.titulo" :checked="tarefa.finalizada"
                @change="alteraStatusTarefa(tarefa)">
            <label :for="tarefa.titulo" :class="{ done: tarefa.finalizada }" class="ms-3">
                {{ tarefa.titulo }}
            </label>
        </li>
    </ul>
</template>

<style scoped>
.done {
    text-decoration: line-through;
}
</style>

<script>
const alteraStatusTarefa = (tarefa) => {
    tarefa.finalizada = !tarefa.finalizada;
};
</script>
