<template>
  <div id="app">
    <!-- v-on is catching sent data -->
    <AddTodo v-on:add-todo="addTodo" />
    <Todos :todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Todos from "../components/Todos";
import AddTodo from "../components/AddTodo";
import axios from "axios";

export default {
  name: "Home",
  components: {
    Todos,
    AddTodo
  },
  // the state/data
  data() {
    return {
      todos: []
    };
  },
  methods: {
    deleteTodo(id) {
      axios
        .delete("https://jsonplaceholder.typicode.com/todos/" + id)
        .then(() => (this.todos = this.todos.filter((todo) => todo.id !== id)))
        .catch((err) => console.log("err :>> ", err));
    },
    addTodo(newTodo) {
      const { title, completed } = newTodo;

      axios
        .post("https://jsonplaceholder.typicode.com/todos", {
          title,
          completed
        })
        .then((res) => (this.todos = [...this.todos, res.data]))
        .catch((err) => console.log("err :>> ", err));
    }
  },
  created() {
    axios
      .get("https://jsonplaceholder.typicode.com/todos?_limit=5")
      .then((res) => (this.todos = res.data))
      .catch((err) => console.log("error :>> ", err));
  }
};
</script>

<style>
body {
  margin: 0;
  padding: 0;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
}
</style>
