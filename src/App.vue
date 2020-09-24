<template>
  <div id="app">
    <div class="Menu">
      <Users />
      <Todos />
      <Photos />
      <Comments />
    </div>
  </div>
</template>

<script>
import Home from "@/components/Home.vue";
import Users from "@/components/Users.vue";
import Todos from "@/components/Todos.vue";
import Photos from "@/components/Photos.vue";
import Comments from "@/components/Comments.vue";

export default {
  name: "App",
  components: {
    Home,
    Users,
    Todos,
    Photos,
    Comments,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
