<template>
  <div class="todo-list">
    <div class="d-flex">
      <img
        alt="Vue logo"
        src="../../assets/logo.png"
        height="32"
        class="mt-1 mr-2"
      />
      <h1 class="display-4">Todo List</h1>
    </div>
    <Form
      :newTodo="newTodo"
      @new-todo-changed="newTodo = $event"
      :todos="todos"
      :search="search"
      @search-changed="search = $event"
    />
    <Todos :todos="todos" :search="search" @delete-todo="deleteTodo" />
  </div>
</template>

<script>
import { v4 as uuidv4 } from "uuid";
import Form from "../form/Form";
import Todos from "../todos/Todos";
export default {
  name: "TodoList",
  components: {
    Form,
    Todos,
  },
  props: {
    msg: String,
  },
  data() {
    return {
      newTodo: "",
      search: "",
      todos: [
        { id: uuidv4(), title: "Get a job", done: true },
        { id: uuidv4(), title: "Learn full stack", done: false },
        { id: uuidv4(), title: "Build SaaS", done: false },
      ],
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
    },
  },
};
</script>

<style lang='scss' scoped>
h1 {
  font-size: 2rem;
}
</style>