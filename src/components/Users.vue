<template>
  <div>
    <button @click="fetchUsers">Users</button>
    <ul>
      <li v-for="(user, index) in users" :key="user.id" v-show="index < 5">
          
        <h4>ID: {{ user.id }}</h4>
        <p>NAME: {{ user.name }}</p>
        <p>USERNAME: {{ user.username }}</p>
        <p>EMAIL: {{ user.email }}</p>
        <p>STREET: {{ user.address.street }}</p>
        <p>SUITE: {{ user.address.suite }}</p>
        <p>CITY: {{ user.address.city }}</p>
        <p>ZIPCODE: {{ user.address.zipcode }}</p>
        <p>LAT: {{ user.address.geo.lat }}</p>
        <p>LNG: {{ user.address.geo.lng }}</p>
        <p>PHONE: {{ user.phone }}</p>
        <p>WEBSITE: {{ user.website }}</p>
        <p>COMPANY NAME: {{ user.company.name }}</p>
        <p>COMPANY CATCH PHRASE: {{ user.company.catchPhrase }}</p>
        <p>COMPANY BS: {{ user.company.bs }}</p>
        <hr>
        <br>
      </li>
    </ul>
    
  </div>
</template>

<script>
export default {
  name: "Users",

  data() {
    return {
      users: [],
      baseURI: "https://jsonplaceholder.typicode.com/users",
    };
  },
  methods: {
    fetchUsers: function () {
      this.$http.get(this.baseURI).then((result) => {
        this.users = result.data;
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