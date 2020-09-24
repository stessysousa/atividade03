<template>
  <div>
    <button @click="fetchTodos">Todos</button>
    <ul>
      <li v-for="todo in todos" :key="todo.id" v-show="todo.userId == 2 && todo.completed" >
        <p>USER ID: {{ todo.userId }}</p>
        <p>ID: {{ todo.id }}</p>
        <p>TITTLE: {{ todo.title }}</p>
        <p>COMPLETED: {{ todo.completed }}</p>
        <hr>
        <br>
      </li>
    </ul>
    
  </div>
</template>

<script>
export default {
  name: "Todos",

  data() {
    return {
      todos: [],
      baseURI: "https://jsonplaceholder.typicode.com/todos",
    };
  },
  methods: {
    fetchTodos: function () {
      this.$http.get(this.baseURI).then((result) => {
        this.todos = result.data;
      });
    },
  },
};
</script>

<style>
li{
  list-style-type: none;
}
</style>