<template>
  <div id="app" class="mt-5">
    <b-container>
      <TodoList />
    </b-container>
  </div>
</template>

<script>
import TodoList from "./components/todoList/TodoList";
export default {
  name: "App",
  components: {
    TodoList,
  },
};
</script>

<style lang="scss">
@import "./scss/custom.scss";
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: $dark;
}
</style>
