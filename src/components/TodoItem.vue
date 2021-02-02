<template>
  <div
    class="todo-item"
    v-bind:class="{ 'is-complete': mutableTodo.completed }"
  >
    <p>
      <input type="checkbox" v-on:change="markComplete()" />
      {{ todo.title }}
    </p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.mutableTodo.completed = !this.mutableTodo.completed;
    }
  },
  data: function() {
    return {
      mutableTodo: this.todo
    };
  }
};
</script>

<style scoped>
.todo-item {
  background: #f3f3f3;
  padding: 1em;
  border-bottom: 1px #ccc dotted;
}

.is-complete {
  text-decoration: line-through;
}
</style>
