<template>
  <b-list-group class="todos mt-2">
    <b-list-group-item
      class="todo d-flex justify-content-between align-items-center"
      v-for="todo in todos"
      :key="todo.id"
      :class="todo.done && 'todo--done'"
    >
      <div>
        <b-form-checkbox :id="todo.id" v-model="todo.done" name="done">
          <p class="todo__title m-0">{{ todo.title }}</p>
        </b-form-checkbox>
      </div>
      <i
        class="todo--delete fas fa-times text-danger mr-1"
        @click="deleteTodo(todos, todo.id, $event)"
      ></i>
    </b-list-group-item>
  </b-list-group>
</template>

<script>
export default {
  name: "Form",
  props: {
    todos: Array,
  },
  methods: {
    deleteTodo: function (todos, id) {
      const indexToDelete = todos.map((todo) => todo.id).indexOf(id);
      todos.splice(indexToDelete, 1);
    },
  },
};
</script>

<style lang='scss' scoped>
@import "../scss/custom.scss";

.todos {
  .todo {
    &.todo--done {
      .todo__title {
        text-decoration: line-through;
      }
    }
  }
}
</style>
