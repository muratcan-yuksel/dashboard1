<template>
  <div v-if="users">
    <div class="textBody" v-for="user in users" :key="user.id">
      <p>Title: {{ user.title }}</p>
      <p>Text: {{ user.body }}</p>
    </div>
  </div>
  <div v-else>
    <h2>Loading...</h2>
  </div>
</template>

<script>
const url = "https://jsonplaceholder.typicode.com/posts";

import axios from "axios";
export default {
  data() {
    return {
      users: null,
    };
  },
  async mounted() {
    const config = {
      method: "get",
      url: url,
    };
    try {
      let res = await axios(config);
      console.log(res.data);
      this.users = res.data.splice(0, 5);
      console.log(this.users);
    } catch (err) {
      console.log(err);
    }
  },
};
</script>

<style scoped>
.textBody {
  border-left: 1px solid grey;
  border-right: 1px solid grey;
  border-bottom: 1px solid grey;
}
</style>
