<template>
  <div>
    <form @submit="addTodo">
      <input type="text" v-model="title" name="title" placeholder="Add todo" />
      <button type="submit" value="Submit">Submit</button>
    </form>
  </div>
</template>

<script>
// import uuid from "uuid";

export default {
  name: "AddTodo",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      console.log('"add todo" :>> ', "add todo");
      const newTodo = {
        title: this.title,
        completed: false
      };
      // send up to parent
      this.$emit("add-todo", newTodo);
      this.title = "";
    }
  }
};
</script>

<style scoped>
div {
  display: flex;
  justify-content: center;
  padding: 0.5rem;
}
form input,
form button {
  padding: 0.3rem;
  border: 1px solid #333;
}
form button {
  background-color: #333;
  color: white;
  font-weight: bold;
}
</style>
