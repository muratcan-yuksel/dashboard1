<template id="usersComponent">
  <div>
    <Navbar />
    <div id="userContainer" v-if="users">
      <b-container class="bv-example-row">
        <b-row>
          <b-col cols="4" sm="4" md="4" lg="4" xl="4">
            <h4>Name</h4>
            <div v-for="user in users" :key="user.id">
              <div class="userNames">{{ user.name }}</div>
            </div></b-col
          >
          <b-col cols="4" sm="4" md="4" lg="4" xl="4">
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
          >
        </b-row>
      </b-container>
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
  margin: 2em;
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
