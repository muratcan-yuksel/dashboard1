<template>
  <div v-if="users">
    <h3>Notes</h3>
    <div class="textBody" v-for="user in users" :key="user.id">
      <p class="noteTitle">{{ user.title }}</p>
      <p class="noteText">{{ user.body }}</p>
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
      this.users = res.data.splice(0, 5);
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
  padding: 1em;
}
.noteTitle {
  font-weight: 500;
}
</style>
