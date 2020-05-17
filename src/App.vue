<template>
  <div id="app">
    <todo-list v-bind:todos="todos"/>
  </div>
</template>

<script>
import TodoList from './components/TodoList'

export default {
  name: 'App',
  components: {
    TodoList
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
  }
}
</script>

<style>
</style>
