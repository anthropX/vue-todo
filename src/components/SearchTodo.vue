<template>
  <b-form-group id="input-group-search-todo" class="flex-grow-0 mb-0 ml-2">
    <b-form-input
      id="search-todo"
      :value="search"
      @input.native="$emit('search-changed', $event.target.value)"
      placeholder="Search"
      required
    />
  </b-form-group>
</template>

<script>
export default {
  name: "SearchTodo",
  props: {
    search: String,
  },
};
</script>