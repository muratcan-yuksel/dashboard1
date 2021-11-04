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
      <!-- add user functionality-->
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
            <!-- <b-col class="userNames">{{ user.name }}</b-col> -->
            <b-col class="userNames">
              <input
                type="text"
                v-model="user.name"
                :disabled="!isEditing"
                :class="{ view: !isEditing }"
            /></b-col>

            <b-col class="userNicks">
              <input
                type="text"
                v-model="user.username"
                :disabled="!isEditing"
                :class="{ view: !isEditing }"
            /></b-col>
            <b-col class="userWebsites">
              <input
                type="text"
                v-model="user.website"
                :disabled="!isEditing"
                :class="{ view: !isEditing }"
            /></b-col>
            <button @click="isEditing = !isEditing" v-if="!isEditing">
              Edit
            </button>
            <button @click="save" v-else-if="isEditing">Save</button>
            <button v-if="isEditing" @click="cancel">Cancel</button>
          </b-row>
        </b-container>
      </div>
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
      isEditing: false,
      users: [],
      name: "",
      username: "",
      website: "",
    };
  },
  methods: {
    save() {
      this.cachedUser = Object.assign({}, this.users);
      this.isEditing = false;
    },
    cancel() {
      this.users = Object.assign({}, this.cachedUser);
      this.isEditing = false;
    },
    addUser() {
      this.users.push({
        name: this.name,
        username: this.username,
        website: this.website,
      });
    },
  },
  async mounted() {
    this.cachedUser = Object.assign({}, this.users);

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
