<template>
  <b-list-group class="todos mt-2">
    <b-list-group-item
      v-for="todo in filteredTodos"
      :key="todo.id"
      :class="todo.done && 'todo--done'"
    >
      <todo :todo="todo" @delete-todo="$emit('delete-todo', $event)" />
    </b-list-group-item>
  </b-list-group>
</template>

<script>
import Todo from "./Todo";
export default {
  name: "Todos",
  components: {
    Todo,
  },
  props: {
    todos: Array,
    search: String,
  },
  computed: {
    filteredTodos() {
      return this.todos.filter((todo) => todo.title.includes(this.search));
    },
  },
};
</script>