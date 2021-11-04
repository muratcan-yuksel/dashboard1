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
        <b-container id="chartsContainer" class="bv-example-row">
          <b-row>
            <b-col cols="12" sm="7" md="7" lg="7" xl="7"><LineChart /></b-col>
            <b-col cols="12" sm="5" md="5" lg="5" xl="5"> <PieChart /></b-col>
          </b-row>
        </b-container>
        <BarChart />
      </div>
    </div>
  </div>
</template>
<script>
//component imports
//navbar
import Navbar from "./components/Navbar.vue";
// cards
import Cards from "./components/Cards.vue";
//line chart
import LineChart from "./components/LineChart.vue";
//pie chart
import PieChart from "./components/PieChart.vue";
//bar chart
import BarChart from "./components/BarChart.vue";
//import vivid icons
import "vivid-icons/dist/vivid-icons.min.js";
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
    LineChart,
    PieChart,
    BarChart,
  },
};
</script>
<style>
#app {
  background-color: rgba(203, 203, 210, 0.15);
}
#cardsDiv {
  margin: 3em;
}
#chartsContainer {
  margin-top: 5em;
}
</style>
