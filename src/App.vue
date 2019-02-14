<template>
  <div id="app" class="container-fluid">
    <jumbotron></jumbotron>
    <completed-todos></completed-todos>
    <hr>
    <get-todo></get-todo>
    <hr>
    <current-todos></current-todos>
  </div>
</template>

<script>
import CompletedTodos from './components/CompletedTodos.vue'
import CurrentTodos from './components/CurrentTodos.vue'
import GetTodo from './components/GetTodo.vue'
import Jumbotron from './components/Jumbotron.vue'

export default {
  name: 'App',
  components: { CompletedTodos, CurrentTodos, GetTodo, Jumbotron }
}
</script>

<style>
.row {
  margin: 1em 0;
}
.btn-group {
  float: right;
}
.btn:focus,
.btn:active:focus,
.btn.active:focus,
.btn.focus,
.btn:active.focus,
.btn.active.focus {
  outline: none;
}
</style>
