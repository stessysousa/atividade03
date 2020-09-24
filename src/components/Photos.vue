<template>
    <div>
      <button @click="fetchPhotos">Photos</button>
    <ul>
      <li v-for="photo in photos" :key="photo.id" v-show="photo.albumId == 3" >
        <img class="img" :src="photo.url">
        <br>
      </li>
    </ul> 
  </div>
</template>

<script>
export default {
  name: "Photos",

  data() {
    return {
      photos: [],
      baseURI: "https://jsonplaceholder.typicode.com/photos",
    };
  },
  methods: {
    fetchPhotos: function () {
      this.$http.get(this.baseURI).then((result) => {
        this.photos = result.data;
      });
    },
  },
};
</script>

<style>
.img{
    width: 100px;
    height: 100px;
}
li{
  list-style-type: none;
}
</style>