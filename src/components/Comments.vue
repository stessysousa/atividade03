<template>
  <div>
    <button @click="fetchComments">Comments</button>
    <ul>
      <li v-for="comment in comments" :key="comment.id" v-show="comment.id % 2 ==0">
        <p>POST ID: {{ comment.postId }}</p>
        <p>ID: {{ comment.id }}</p>
        <p>NOME: {{ comment.name }}</p>
        <p>EMAIL: {{ comment.email }}</p>
        <p>BODY: {{ comment.body }}</p>
        <hr>
        <br>
      </li>
    </ul>
    
  </div>
</template>

<script>
export default {
  name: "Comments",

  data() {
    return {
      comments: [],
      baseURI: "https://jsonplaceholder.typicode.com/comments",
    };
  },
  methods: {
    fetchComments: function () {
      this.$http.get(this.baseURI).then((result) => {
        this.comments = result.data;
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