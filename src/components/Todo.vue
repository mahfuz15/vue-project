<template>
    <div>
        <div :class="{'isCompleted':todo_data.completed}">
            <input type="checkbox" @change="markComplete" :checked="todo_data.completed">
            <p>{{todo_data.title}}</p>
            <button @click="$emit('del-todo', todo_data.id)">delete</button>
        </div>
    </div>
</template>

<script>
export default {
    name: "Todo",
    props: ["todo"],
    data(){
        return {
            todo_data : this.todo
        }
    },
    methods: {
        markComplete () {
            this.todo_data.completed = !this.todo_data.completed
        }
    }
}
</script>

<style scoped>
.isCompleted {
    text-decoration: line-through;
}
</style>