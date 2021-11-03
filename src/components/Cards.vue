<template>
  <!-- this div will get flex wrap OR
bootstrap -->
  <b-container class="cardComponentContainer">
    <b-row>
      <!-- card container will get flex column -->
      <b-col cols="12" sm="6" md="3" lg="3" xl="3" class="cardContainer">
        <!-- card content will get flex row AND
      justify content space between AND
      bottom border 1 px solid grey -->
        <div class="cardContent">
          <div class="icon"></div>
          <div class="cardText">Some text</div>
        </div>
        <div class="cardB"></div>
      </b-col>
      <b-col cols="12" sm="6" md="3" lg="3" xl="3" class="cardContainer">
        <!-- card content will get flex row AND
      justify content space between AND
      bottom border 1 px solid grey -->
        <div class="cardContent">
          <div class="icon"></div>
          <div class="cardText">Some text</div>
        </div>
        <div class="cardB"></div>
      </b-col>
      <b-col cols="12" sm="6" md="3" lg="3" xl="3" class="cardContainer">
        <!-- card content will get flex row AND
      justify content space between AND
      bottom border 1 px solid grey -->
        <div class="cardContent">
          <div class="icon"></div>
          <div class="cardText">Some text</div>
        </div>
        <div class="cardB"></div>
      </b-col>
      <b-col cols="12" sm="6" md="3" lg="3" xl="3" class="cardContainer">
        <!-- card content will get flex row AND
      justify content space between AND
      bottom border 1 px solid grey -->
        <div class="cardContent">
          <div class="icon"></div>
          <div class="cardText">Some text</div>
        </div>
        <div class="cardB"></div>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {};
</script>

<style scoped>
/* #cardComponentContainer {
  display: flex;
  flex-wrap: wrap;
} */
.cardContainer {
  border: 1px solid black;
}
</style>
