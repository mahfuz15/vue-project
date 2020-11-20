<template>
    <div class="todos">
        <h1>Todos</h1>
        <div>
            <div v-for="todo in todos" :key="todo.id">
                <Todo :todo="todo"  v-on:del-todo="$emit('del-todo', todo.id)"/>
            </div>
        </div>
    </div>    
</template>

<script>
import Todo from './Todo';
export default {
    name: 'Todos',
    components: {
        Todo
    },
    props: ["todos"]
}
</script>

<style scoped>

</style>