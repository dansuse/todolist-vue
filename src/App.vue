<template>
  <div id="app">
    <todo-list v-bind:todos="todos"/>
    <create-todo v-on:create-todo="addTodo"/>
  </div>
</template>

<script>
import TodoList from './components/TodoList'
import CreateTodo from './components/CreateTodo'

export default {
  name: 'App',
  components: {
    TodoList,
    CreateTodo
  },
  data: function () {
    return {
      todos: [
        {
          title: 'Todo A',
          project: 'Project A',
          done: false
        },
        {
          title: 'Todo B',
          project: 'Project B',
          done: true
        }
      ]
    }
  },
  methods: {
    addTodo (todo) {
      this.todos.push(todo)
    }
  }
}
</script>

<style>
</style>
