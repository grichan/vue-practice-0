<template>
  <div id="app">
    <Todos :todos="todos" />
  </div>
</template>

<script>
import Todos from "./components/Todos";

export default {
  name: "App",
  components: {
    Todos
  },
  // the state/data
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "todo 1",
          completed: false
        },
        {
          id: 2,
          title: "todo 2",
          completed: true
        },
        {
          id: 3,
          title: "todo 3",
          completed: false
        }
      ]
    };
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
