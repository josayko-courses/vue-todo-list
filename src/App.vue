<template>
  <h1>Todo List</h1>
  <form action="">
    <input v-model="addTodoInput" type="text" />
    <button @click.prevent="addTodo">Add</button>
  </form>

  <p><input v-model="hideCompleted" type="checkbox" /> Hide completed</p>

  <div>
    <ul v-if="todos.length">
      <li v-for="(todo, index) in todos" :key="index">
        <p v-if="!(todo.completed && hideCompleted)">
          <input v-model="todo.completed" @change="sortTodos()" type="checkbox" />
          <span :class="{ 'line-through': todo.completed }">
            {{ ` ${todo.title} (${todo.date.toLocaleString('fr')})` }}
          </span>
          <button :style="{ 'margin-left': '1em' }" @click="deleteTodo(index)">X</button>
        </p>
      </li>
    </ul>
    <p v-else>No todos !</p>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

type Todo = {
  title: string
  completed: boolean
  date: Date
}

const addTodoInput = ref('')
const todos = ref<Todo[]>([])
const hideCompleted = ref(false)

function sortTodos() {
  todos.value.sort((a, b) => {
    if (a.completed && !b.completed) {
      return 1
    } else if (!a.completed && b.completed) {
      return -1
    } else {
      return a.date < b.date ? -1 : 1
    }
  })
}

function addTodo() {
  todos.value.push({
    title: addTodoInput.value,
    completed: false,
    date: new Date()
  })
  sortTodos()
  addTodoInput.value = ''
}

function deleteTodo(index: number) {
  todos.value.splice(index, 1)
}
</script>

<style lang="css">
li {
  list-style-type: none;
}

.line-through {
  text-decoration: line-through;
}
</style>
