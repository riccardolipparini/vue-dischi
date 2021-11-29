<template>
  <div id="container-big">
      <div class="containcards">
          <div class="cards">
              <img src="" alt="">
              <h1></h1>
              <h4></h4>
              <h4></h4>
          </div>
      </div>
  </div>
</template>

<script>
export default {
  name: "Selezione",
  components: {},
};
</script>

<style lang="scss">
#container-big {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: rgb(42, 43, 66);
  .containcards{
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      height: 700px;
      width: 80%;
      .cards{
          text-align: center;
          height: 40%;
          width: calc(90% / 5);
          background-color: rgb(36, 37, 47);
          img{
              width: 150px;
          }
          h1{
              color: white;
          }
          h4{
              color: lightgray;
          }
      }
  }
}
</style>