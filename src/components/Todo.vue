<template>
  <div class="todo w-100 d-flex justify-content-between align-items-center">
    <b-form-checkbox :id="todo.id" v-model="todo.done" name="done">
      <p class="todo__title m-0">{{ todo.title }}</p>
    </b-form-checkbox>
    <i
      class="todo--delete fas fa-times text-danger mr-1"
      @click="$emit('delete-todo', todo.id)"
    ></i>
  </div>
</template>

<script>
export default {
  name: "Todo",
  props: {
    todo: Object,
  },
};
</script>

<style lang='scss' scoped>
@import "../scss/custom.scss";
.todo {
  &.todo--done {
    .todo__title {
      text-decoration: line-through;
    }
  }
}
</style>
