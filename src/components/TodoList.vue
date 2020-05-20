<template>
    <div>
        <p>Completed Tasks: {{ todos.filter(todo => {return todo.done === true}).length }}</p>
        <p>Pending Tasks: {{ todos.filter(todo => {return todo.done === false}).length }}</p>
        <Todo v-on:complete-todo='completeTodo' v-on:delete-todo='deleteTodo' v-for="(todo, index) in todos" v-bind:todo="todo" v-bind:key="index">
        </Todo>
    </div>
</template>

<script type="text/javascript">

import Todo from './Todo'

export default{
  props: ['todos'],
  components: {
    Todo
  },
  methods: {
    deleteTodo (todo) {
      const todoIndex = this.todos.indexOf(todo)
      this.todos.splice(todoIndex, 1)
    },
    completeTodo (todo) {
      const todoIndex = this.todos.indexOf(todo)
      this.todos[todoIndex].done = true
    }
  }
}

</script>

<style>

</style>
