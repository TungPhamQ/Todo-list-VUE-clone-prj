<template>
    <div class="todo-item" :class="{ 'is-complete': todo.completed }">
        <p>
            <input type="checkbox" v-on:change="markFinish">
            {{ todo.title }}
            <button @click="$emit('del-todo', todo.id)" class="del">x</button>
        </p>
    </div>
</template>

<script>
export default {
    name: "ToDosItem",
    props: ['todo'],
    data() {
        return {
            Todo: this.todo,
        }
    },
    methods: {
        markFinish() {
            this.Todo.completed = !this.Todo.completed;
        }
    }
}
</script>

<style scoped>
.todo-item {
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
}

.is-complete {
    text-decoration: line-through;
}

.del {
    background: #ff0000;
    color: #fff;
    border: none;
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
}
</style>