<template>
	<div class="todos">
		<div v-for="todo in todos" :key="todo.id">
			<ToDosItem :todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" />
		</div>

	</div>
</template>

<script>
import ToDosItem from './ToDosItem.vue'
export default {
	name: 'ToDosList',
	props: ['todos'],
	components: {
		ToDosItem
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
