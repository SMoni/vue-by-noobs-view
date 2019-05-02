<template>
	<div>
		<ul v-if="todos.length">
			<todo-Item
				v-for="todo in todos"
				:key="todo.id"
				:todo="todo"
				@remove="removeTodo"
			/>
		</ul>
	</div>
</template>

<script>
import TodoItem from '@/components/ToDo/Item.vue'

let nextTodoId = 1

export default {
  name: 'TodoList',
	components: {
		TodoItem
	},
  data () {
    return {
			newTodoText: '',
      todos: [
				{
					id: nextTodoId++,
					text: 'Learn Vue'
				},
				{
					id: nextTodoId++,
					text: 'Learn about single-file components'
				},
				{
					id: nextTodoId++,
					text: 'Fall in love'
				}
			]
    }
  },
	methods: {
		addTodo () {
			const trimmedText = this.newTodoText.trim()
			if (trimmedText) {
				this.todos.push({
					id: nextTodoId++,
					text: trimmedText
				})
				this.newTodoText = ''
			}
		},
		removeTodo (idToRemove) {
			this.todos = this.todos.filter(todo => {
				return todo.id !== idToRemove
			})
		}
	}
}
</script>
