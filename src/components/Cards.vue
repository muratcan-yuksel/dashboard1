<template>
  <b-container class="cardComponentContainer">
    <b-row>
      <b-col cols="12" sm="6" md="3" lg="3" xl="3" class="cardContainer">
        <!-- card content will get flex row AND
      justify content space between AND
      bottom border 1 px solid grey -->
        <div class="cardContent">
          <div class="icon"><i data-vi="cog"></i></div>
          <div class="cardText">Some text</div>
        </div>
        <div class="cardBottom">Updated now</div>
      </b-col>
      <b-col cols="12" sm="6" md="3" lg="3" xl="3" class="cardContainer">
        <!-- card content will get flex row AND
      justify content space between AND
      bottom border 1 px solid grey -->
        <div class="cardContent">
          <div class="icon"><i data-vi="gem"></i></div>
          <div class="cardText">Some text</div>
        </div>
        <div class="cardBottom">First day</div>
      </b-col>
      <b-col cols="12" sm="6" md="3" lg="3" xl="3" class="cardContainer">
        <!-- card content will get flex row AND
      justify content space between AND
      bottom border 1 px solid grey -->
        <div class="cardContent">
          <div class="icon"><i data-vi="graph-poly"></i></div>
          <div class="cardText">Some text</div>
        </div>
        <div class="cardBottom">Last day</div>
      </b-col>
      <b-col cols="12" sm="6" md="3" lg="3" xl="3" class="cardContainer">
        <!-- card content will get flex row AND
      justify content space between AND
      bottom border 1 px solid grey -->
        <div class="cardContent">
          <div class="icon"><i data-vi="bullhorn"></i></div>
          <div class="cardText">Some text</div>
        </div>
        <div class="cardBottom">Updated</div>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {};
</script>

<style scoped>
/* #cardComponentContainer {
 
} */
.cardContainer {
  border-bottom: 1px solid black;
  height: 10em;
  border-left: 1px solid black;
}
.cardContent {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px dashed grey;
}
.cardText {
  font-weight: 900;
}
.cardBottom {
  /* margin-top: 2em; */
  padding-top: 2em;
  color: rgb(194, 189, 189);
}
</style>
