<template>
  <div id="container-big">
    <div class="containcards">
      <Cards v-for="(song, i) in canzoni" :key="i" :details="song" />
    </div>
  </div>
</template>



<script>
import axios from "axios";
import Cards from "@/components/Cards.vue";

export default {
  name: "Selezione",
  components: {
    Cards,
  },
  data() {
    return {
      apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
      canzoni: [],
    };
  },
  created() {},
  methods: {
    getCards() {
      axios.get(this.apiUrl).then((result) => {
        this.canzoni = result.data;
      });
    },
  },
};
</script>

<style lang="scss">
#container-big {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: rgb(42, 43, 66);
  .containcards {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    height: 700px;
    width: 80%;
    .cards {
      text-align: center;
      height: 40%;
      width: calc(90% / 5);
      background-color: rgb(36, 37, 47);
      img {
        width: 150px;
      }
      h1 {
        color: white;
      }
      h4 {
        color: lightgray;
      }
    }
  }
}
</style>