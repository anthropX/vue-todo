<template>
  <div class="w-100 d-flex">
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
      @click="newTodo && addTodo(newTodo)"
      variant="success"
      >Add to list</b-button
    >
  </div>
</template>

<script>
import { v4 as uuidv4 } from "uuid";
export default {
  name: "AddTodo",
  props: {
    newTodo: String,
    todos: Array,
  },
  methods: {
    addTodo() {
      this.todos.push({ id: uuidv4(), title: this.newTodo, done: false });
    },
  },
};
</script>