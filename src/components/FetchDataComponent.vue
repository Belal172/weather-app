<template>
  <div>
    <h1>Random User</h1>
    <p>Name: {{ user.name }}</p>
    <p>Email: {{ user.email }}</p>
  </div>
</template>

<script>
import axios from 'axios'
export default {
    name:'FetchDataComponent',
  data() {
    return {
      user: {}
    };
  },
  async mounted() {
    const response = await axios.get("https://jsonplaceholder.typicode.com/users/2");
    this.user = response.data;
  }
};
</script>

