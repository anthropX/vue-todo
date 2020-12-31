<template>
  <b-form class="d-flex">
    <AddTodo
      :newTodo="newTodo"
      @new-todo-changed="$emit('new-todo-changed', $event)"
      :todos="todos"
    />
    <SearchTodo
      :search="search"
      @search-changed="$emit('search-changed', $event)"
    />
  </b-form>
</template>

<script>
import AddTodo from "./AddTodo";
import SearchTodo from "./SearchTodo";
export default {
  name: "Form",
  components: {
    AddTodo,
    SearchTodo,
  },
  props: {
    newTodo: String,
    search: String,
    todos: Array,
  },
};
</script>