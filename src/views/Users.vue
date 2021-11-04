<template id="usersComponent">
  <div>
    <Navbar />
    <div id="userContainer" v-if="users">
      <b-container class="bv-example-row">
        <b-row>
          <b-col> <h4>Name</h4></b-col>
          <b-col> <h4>User Name</h4></b-col>
          <b-col> <h4>Website</h4></b-col>
        </b-row>
      </b-container>
      <!-- editing functionality-->
      <b-container class="bv-example-row">
        <b-row>
          <b-col cols="3"> <input v-model="name" placeholder="name" /></b-col>
          <b-col cols="3">
            <input v-model="username" placeholder="user name"
          /></b-col>
          <b-col cols="3">
            <input v-model="website" placeholder="website"
          /></b-col>
          <b-col cols="3">
            <button @click="addUser">Add new user</button>
          </b-col>
        </b-row>
      </b-container>

      <div v-for="user in users" :key="user.id">
        <b-container class="bv-example-row">
          <b-row>
            <b-col class="userNames">{{ user.name }}</b-col>
            <b-col class="userNicks">{{ user.username }}</b-col>
            <b-col class="userWebsites">{{ user.website }}</b-col>
          </b-row>
        </b-container>
      </div>
      >
      <!-- <b-col cols="4" sm="4" md="4" lg="4" xl="4">
            <h4>UserName</h4>
            <div v-for="user in users" :key="user.id">
              <div class="userNicks">{{ user.username }}</div>
            </div></b-col
          >
          <b-col cols="4" sm="4" md="4" lg="4" xl="4">
            <h4>Website</h4>
            <div v-for="user in users" :key="user.id">
              <div class="userWebsites">{{ user.website }}</div>
            </div></b-col
          > -->
    </div>
    <div v-else>
      <h4>Loading...</h4>
    </div>
  </div>
</template>

<script>
//navabr import
import Navbar from "../components/Navbar.vue";
const url = "https://jsonplaceholder.typicode.com/users";

import axios from "axios";
export default {
  components: { Navbar },
  data() {
    return {
      users: [],
      name: "",
      username: "",
      website: "",
    };
  },
  methods: {
    addUser() {
      this.users.push({
        name: this.name,
        username: this.username,
        website: this.website,
      });
    },
  },
  async mounted() {
    const config = {
      method: "get",
      url: url,
    };
    try {
      let res = await axios(config);
      console.log(res.data);

      this.users = res.data;
    } catch (err) {
      console.log(err);
    }
  },
};
</script>

<style scoped>
#usersComponent {
  background-color: rgba(203, 203, 210, 0.15);
}
#userContainer {
  border: 1px solid black;
  margin-top: 2em;
  padding: 10px;
  box-shadow: 5px 10px #888888;
}
.userNames {
  border: 1px solid grey;
  background-color: white;
}
.userNicks {
  border: 1px solid grey;
  background-color: white;
}
.userWebsites {
  border: 1px solid grey;
  background-color: white;
}
</style>
