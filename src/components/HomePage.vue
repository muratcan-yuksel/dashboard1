<template>
  <h1>Dashboard</h1>
</template>

<script>
const url = "https://jsonplaceholder.typicode.com/users";
import Vue from "vue";
import { BootstrapVue, IconsPlugin } from "bootstrap-vue";

// Import Bootstrap an BootstrapVue CSS files (order is important)
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap-vue/dist/bootstrap-vue.css";

// Make BootstrapVue available throughout your project
Vue.use(BootstrapVue);
// Optionally install the BootstrapVue icon components plugin
Vue.use(IconsPlugin);
import axios from "axios";
export default {
  async mounted() {
    // let res = await axios.get(url);
    // let data = res.data;
    // console.log(data);
    const config = {
      method: "get",
      url: url,
    };
    let res = await axios(config);
    console.log(res.data);
  },
};
</script>

<style></style>
