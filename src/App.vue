<template>
  <div id="app">
    <Nav></Nav>
    <div id="nav">
      <!-- <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> -->
    </div>
    <router-view />
  </div>
</template>
<script>
// @ is an alias to /src
import Nav from "@/components/Nav.vue";

export default {
  components: {
    Nav
  }
};
</script>

<style lang="scss">
ul,
p,
body {
  margin: 0;
  padding: 0;
}
li {
  list-style: none;
}
a {
  text-decoration: none;
  color: #000;
}
#app {
  .Nav-hader {
    padding: 0;
  }
}
</style>
