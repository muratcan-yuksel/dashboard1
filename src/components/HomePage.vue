<template>
  <div>
    <!-- <b-button variant="danger">Button</b-button> -->
  </div>
</template>

<script>
const url = "https://jsonplaceholder.typicode.com/users";

import axios from "axios";
export default {
  async mounted() {
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
