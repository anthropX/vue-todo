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
      @click="newTodo && todos.push({ title: newTodo, done: false })"
      variant="success"
      >Add to list</b-button
    >
  </b-form>
</template>

<script>
export default {
  name: "Form",
  props: {
    newTodo: String,
    todos: Array,
  },
};
</script>
