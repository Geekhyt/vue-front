<template>
  <ul id="app">
    <li v-for="(user) in users" :key="user.id">
        {{user.name}}
    </li>
  </ul>
</template>

<script>
import axios from 'axios';
export default {
  name: 'App',
  data() {
      return {
          users: []
      }
  },
  mounted() {
      axios.get('http://47.104.94.75:5000/api/users').then(response => {
          console.log(response.data);
          this.users = response.data;
      })
  }
}
</script>

<style>

</style>
