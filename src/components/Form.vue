<template>
  <b-form class="d-flex">
    <b-form-group id="form-group" class="flex-grow-1 mb-0 mr-2">
      <b-form-input
        id="form-input-new-todo"
        v-model="newTodo"
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
        v-model="search"
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
    todos: Array,
    search: String,
  },
};
</script>