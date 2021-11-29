<template>
<header>
    <div id="spotify">
      <img
        src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/74/Spotify_App_Logo.svg/2048px-Spotify_App_Logo.svg.png"
        alt=""
      />
      <div id="cerca">
        <input type="text" placeholder="search" v-model.trim="inputUtente" />
        <button @click.prevent="ricerca">search</button>
      </div>
    </div>
  <div id="container-big">
    <div class="containcards">
      <Cards v-for="(song, i) in filtraSong" :key="i" :details="song" />
    </div>
  </div>
</header>
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
      imputUtente: "",
      searchText: "",
    };
  },
  created() {
    this.getCards();
  },
  computed:{
      filtraSong(){
          if(this.searchText === ""){
              return this.canzoni;
          }
          return this.canzoni.filter((item) => {
              return item.title.toLowerCase().includes(this.searchText.toLowerCase())
          })
      }
  },

  methods: {
    getCards() {
      axios.get(this.apiUrl).then((result) => {
        this.canzoni = result.data.response;
      });
    },
    ricerca(){
        this.searchText = this.imputUtente;
    }
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
  }
}
#spotify {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 100px;
  width: 100%;
  background-color: grey;
  img {
    width: 80px;
    height: 80px;
  }
}
</style>