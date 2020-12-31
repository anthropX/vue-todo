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
      @click="$emit('add-todo-clicked')"
      variant="success"
      >Add to list</b-button
    >
  </div>
</template>

<script>
export default {
  name: "AddTodo",
  props: {
    newTodo: String,
    todos: Array,
  },
};
</script>