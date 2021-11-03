<template>
  <div>
    <div id="app">
      <!-- <div id="nav">
        <router-link to="/">Home</router-link> |
        <router-link to="/about">About</router-link>
      </div> -->
      <router-view />
      <Navbar />
      <div id="cardsDiv">
        <Cards />
      </div>
    </div>
  </div>
</template>
<script>
//import vivid icons
import "vivid-icons/dist/vivid-icons.min.js";
//navbar import
import Navbar from "./components/Navbar.vue";
//import cards
import Cards from "./components/Cards.vue";
//import bootstrap vue here
import Vue from "vue";
import { BootstrapVue, IconsPlugin } from "bootstrap-vue";

// Import Bootstrap an BootstrapVue CSS files (order is important)
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap-vue/dist/bootstrap-vue.css";

// Make BootstrapVue available throughout your project
Vue.use(BootstrapVue);
// Optionally install the BootstrapVue icon components plugin
Vue.use(IconsPlugin);
export default {
  components: {
    Navbar,
    Cards,
  },
};
</script>
<style>
#cardsDiv {
  margin: 3em;
}
</style>
