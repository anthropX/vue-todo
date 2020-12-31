<template>
  <b-form class="d-flex">
    <b-form-group id="form-group" class="flex-grow-1 mb-0 mr-2">
      <b-form-input
        id="form-input-new-todo"
        :value="newTodo"
        @input.native="$emit('new-todo-changed', $event.target.value)"
        placeholder="What do you plan to do?"
        required
      ></b-form-input>
    </b-form-group>
    <b-button
      class="text-nowrap"
      @click="newTodo && todos.push({ title: newTodo, done: false })"
      variant="success"
      >Add to list</b-button
    >
    <b-form-group id="input-group-search-todo" class="flex-grow-0 mb-0 ml-2">
      <b-form-input
        id="search-todo"
        :value="search"
        @input.native="$emit('search-changed', $event.target.value)"
        placeholder="Search"
        required
      />
    </b-form-group>
  </b-form>
</template>

<script>
export default {
  name: "Form",
  props: {
    newTodo: String,
    search: String,
    todos: Array,
  },
};
</script>