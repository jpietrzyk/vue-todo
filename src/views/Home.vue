<template>
  <div id="app">
    <div class="container">
      <AddTodo/>
      <FilterTodos/>
      <Todos/>
    </div>
  </div>
</template>

<script>
import Todos from '../components/Todos';
import AddTodo from '../components/AddTodo';
import FilterTodos from '../components/FilterTodos';
export default {
  name: 'Home',
  components: {
    Todos,
    AddTodo,
    FilterTodos
  },
  data() {
    return {
      todos: []
    }
  },
  methods: {

  },
}
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
  .btn {
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }
  .btn:hover {
    background: #666;
  }
</style>
