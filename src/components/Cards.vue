<template>
  <div class="cards">
    <img :src="details.poster" alt="" />
    <h1>{{details.title}}</h1>
    <h4>{{details.author}}</h4>
    <h4>{{details.year}}</h4>
  </div>
</template>

<script>
export default {
  name: "Cards",
  props: {
      details: Object
  }

};
</script>

<style lang="scss">
.cards {
  text-align: center;
  height: 45%;
  width: calc(90% / 5);
  background-color: rgb(36, 37, 47);
  img {
    width: 150px;
  }
  h1 {
    color: white;
    font-size: 20px;
  }
  h4 {
    color: lightgray;
  }
}
</style>