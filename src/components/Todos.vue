<template>
  <div>
    <h3>Todos:</h3>
    <div class="todos">
      <div :key="todo.id" v-for="todo in allTodos">
        <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" />
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters, mapActions } from 'vuex';
import TodoItem from './TodoItem';
export default {
  name: "Todods",
  methods: mapActions(['fetchTodos']),
  computed: mapGetters(['allTodos']),
  created() {
    this.fetchTodos();
  },
  components: {
    TodoItem
  },
  props: ["todos"]
}
</script>

<style scoped>
  .todos {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 1rem;
  }
</style>
