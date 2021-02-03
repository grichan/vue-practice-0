<template>
  <header class="header">
    <h1>TodoList</h1>
    <div id="nav">
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header"
};
</script>

<style scoped>
.header {
  display: flex;
  flex-direction: column;
  text-align: center;
  background-color: #333;
  color: white;
}

#nav {
  display: flex;
  flex-direction: row;
  justify-content: center;
  max-width: auto;
  padding: 1rem 0;
  background-color: #333;
  color: white;
}

#nav a {
  padding: 0 0.3rem;
  color: white;
}
</style>
