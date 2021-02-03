<template>
  <div>
    <form @submit="addTodo">
      <input type="text" v-model="title" name="title" placeholder="Add todo" />
      <input type="submit" value="Submit" />
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

<style scoped></style>
