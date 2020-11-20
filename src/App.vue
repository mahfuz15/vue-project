<template>
  <Todos :todos="todos" v-on:del-todo="deleteTodo"/>
</template>

<script>
import Todos from './components/Todos';
export default {
  name: 'App',
  components: {
    Todos
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "API integration",
          completed: false 
        },
        {
          id: 2,
          title: "Install Vue",
          completed: true 
        },
        {
          id: 3,
          title: "Deploy Project",
          completed: false 
        }
      ]
    }
  },
  methods: {
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id != id);
    }
  }
}
</script>

<style>

</style>
