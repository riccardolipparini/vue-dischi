<template>
  <div id="app">
    <header id="banner-logo">
        <!-- <img src="@/assets/logo-spotify.png" alt=""> -->
      <div id="cont-select">
        <!-- :list="listGen" -->
          <Filterselect  :list="newListGenFromSon" @search="selectOption"/>
      </div>
    </header>
    <main>
      <Selezione :details="optionChoise" @newListDisk="creationList"/>
    </main>
  </div>
</template>

<script>
import Filterselect from '@/components/Filterselect.vue'
import Selezione from './components/Selezione.vue'
// import MyHeader from './components/MyHeader.vue'
export default {
  name: 'App',
  components: {
    // MyHeader,
    Selezione,
    Filterselect,
  },
  data() {
    return {
      optionChoise: "all",
      newListGenFromSon: null,
    }
  },
  computed: {
    listGen2(){
      return this.listGen3
    }
  },
  methods: {
    // salvo il valore della scelta utente
    selectOption(genere){
      this.optionChoise = genere;
      console.log("hai selezionato: ",this.optionChoise);
    },
    creationList(item){
      this.newListGenFromSon = item
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
main {
  background-color: #1e2d3b;
  min-height: calc(100vh - 80px);
}
#banner-logo {
  height: 80px;
  background-color: #2e3a46;
  display: flex;
  align-items: center;
  justify-content: flex-end;
}
#cont-select {
  text-align: end;
  padding: 10px 0;
}
</style>
