<template>
  <!-- this div will get flex wrap OR
bootstrap -->
  <div>
    <!-- card container will get flex column -->
    <div class="cardContainer">
      <!-- card content will get flex row AND
      justify content space between AND
      bottom border 1 px solid grey -->
      <div class="cardContent">
        <div class="icon"></div>
        <div class="cardText">Some text</div>
      </div>
      <div class="cardB"></div>
    </div>
    <div class="cardContainer">
      <!-- card content will get flex row AND
      justify content space between AND
      bottom border 1 px solid grey -->
      <div class="cardContent">
        <div class="icon"></div>
        <div class="cardText">Some text</div>
      </div>
      <div class="cardB"></div>
    </div>
    <div class="cardContainer">
      <!-- card content will get flex row AND
      justify content space between AND
      bottom border 1 px solid grey -->
      <div class="cardContent">
        <div class="icon"></div>
        <div class="cardText">Some text</div>
      </div>
      <div class="cardB"></div>
    </div>
    <div class="cardContainer">
      <!-- card content will get flex row AND
      justify content space between AND
      bottom border 1 px solid grey -->
      <div class="cardContent">
        <div class="icon"></div>
        <div class="cardText">Some text</div>
      </div>
      <div class="cardB"></div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.cardContainer {
  border: 1px solid black;
  height: 50px;
  width: 50px;
}
</style>
