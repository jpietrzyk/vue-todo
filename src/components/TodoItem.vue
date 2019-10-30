<template>
  <div>
    <div @dblclick="onDblClick(todo)" class="todo-item" v-bind:class="{'is-complete':todo.completed}">
      {{todo.title}}
      <i @click="deleteTodo(todo.id)" class="fas fa-trash-alt"></i>
    </div>
  </div>
</template>

<script>
import { mapActions } from 'vuex';
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    ...mapActions(["deleteTodo", "updateTodo"]),
    onDblClick(todo) {
      const updTodo = {
        id: todo.id,
        title: todo.title,
        completed: !todo.completed
      }

      this.updateTodo(updTodo);
    }
  }
}
</script>

<style scoped>
  .todo-item {
    border: 1px solid #ccc;
    background: #41b883;
    padding: 1rem;
    border-radius: 5px;
    text-align: center;
    position: relative;
    cursor: pointer;
  }

  i {
    position: absolute;
    bottom: 10px;
    right: 10px;
    color: #ffffff;
    cursor: pointer;
  }

  .is-complete {
    background: #35495e;
    color: #fff;
  }
</style>
