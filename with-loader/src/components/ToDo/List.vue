<template>
	<div class="todo-list">
    <todo-input
      v-model="newTodoText"
      placeholder="Mit Enter neu anlegen..."
      @keydown.enter="addTodo" 
    />
    <todo-item
      v-for="todo in todos"
      :key="todo.id"
      :item="todo"
      @remove="removeTodo"
    />
	</div>
</template>

<script>
import uuid  from 'uuid/v1'
//
import TodoItem  from '@/components/Todo/Item.vue'
import TodoInput from '@/components/Todo/Input.vue'

function createTodoWith(text) {
  return {
    id:   uuid(),
    text: text
  }
}

export default {
  name: 'TodoList',
	components: {
    TodoItem,
    TodoInput
	},
  data () {
    return {
			newTodoText: '',
      todos: [
        createTodoWith('Präsentation'),
        createTodoWith('Demo script-include'),
        createTodoWith('Demo vue-cli')
			]
    }
  },
	methods: {
		addTodo () {

			const trimmedText = this.newTodoText.trim()

      if (!trimmedText) {
        return
      }

      const newItem = [createTodoWith(trimmedText)]

      this.todos = this.todos
        .concat(newItem)

      this.newTodoText = ''
		},
		removeTodo (idToRemove) {
      this.todos = this.todos
        .filter(todo => todo.id !== idToRemove)
		}
	}
}
</script>
