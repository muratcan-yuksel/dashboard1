<template>
  <div>
    <div id="app">
      <!-- <div id="nav">
        <router-link to="/">Home</router-link> |
        <router-link to="/about">About</router-link>
      </div> -->
      <Navbar />
      <div id="cardsDiv">
        <Cards />
        <b-container id="chartsContainer" class="bv-example-row">
          <b-row>
            <b-col cols="12" sm="7" md="7" lg="7" xl="7"><LineChart /></b-col>
            <b-col cols="12" sm="5" md="5" lg="5" xl="5"> <PieChart /></b-col>
          </b-row>
        </b-container>
        <div id="chartAnd">
          <b-container class="bv-example-row">
            <b-row>
              <b-col cols="12" sm="6" md="6" lg="6" xl="6"><BarChart /></b-col>
              <b-col cols="12" sm="6" md="6" lg="6" xl="6"> <Notes /></b-col>
            </b-row>
          </b-container>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
//component imports
//navbar
import Navbar from "./Navbar.vue";
// cards
import Cards from "./Cards.vue";
//line chart
import LineChart from "./LineChart.vue";
//pie chart
import PieChart from "./PieChart.vue";
//bar chart
import BarChart from "./BarChart.vue";
//notes
import Notes from "./Notes.vue";
//////
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
    Notes,
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
