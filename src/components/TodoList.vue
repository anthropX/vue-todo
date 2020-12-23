<template>
  <div class="todo-list">
    <div class="d-flex">
      <img alt="Vue logo" src="../assets/logo.png" height='32' class='mt-1 mr-2'/>
      <h1 class="display-4">Todo List</h1>
    </div>
    <Form :newTodo="newTodo" :todos="todos" />
    <Todos :todos="todos" />
  </div>
</template>

<script>
import { v4 as uuidv4 } from "uuid";
import Form from "./Form.vue";
import Todos from "./Todos.vue";
export default {
  name: "TodoList",
  props: {
    msg: String,
  },
  data() {
    return {
      newTodo: "",
      todos: [
        { id: uuidv4(), title: "Get a job", done: true },
        { id: uuidv4(), title: "Learn full stack", done: false },
        { id: uuidv4(), title: "Build SaaS", done: false },
      ],
    };
  },
  components: {
    Form,
    Todos,
  },
};
</script>

<style lang='scss' scoped>
h1 {
  font-size: 2rem;
}
</style>