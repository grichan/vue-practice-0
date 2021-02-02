<template>
  <div
    class="todo-item"
    v-bind:class="{ 'is-complete': mutableTodo.completed }"
  >
    <p>
      <input
        type="checkbox"
        v-on:change="markComplete()"
        :checked="mutableTodo.completed"
      />
      {{ todo.title }}
    </p>
    <button @click="$emit('del-todo', todo.id)" class="del">x</button>
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
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.is-complete {
  text-decoration: line-through;
}

.del {
  background-color: rgba(255, 75, 75, 0.849);
}
</style>
