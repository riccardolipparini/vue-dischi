<template>
<div>
  <div id="container">
    <Cards 
    v-for="disk, i in filteredListCards" 
    :key="i" 
    :details="disk"/> 
    
  </div>
</div>
  
</template>

<script>
import Cards from '@/components/Cards.vue'
import Axios from 'axios'
export default {
  name: "Selezione",
  components: {
    Cards,
  },
  props: {
    details:String
  },
  data() {
    return {
      
        apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
        listDisk: [],
        listGen: [],
    };
  },
  created(){
    this.getArray();
    this.$emit('newListDisk', this.listGen)
  },
  computed:{
    // creo un nuovo array per filtrare i contenuti in pagina
    filteredListCards(){
      if(this.details === "all"){
        return this.listDisk
      }
      return this.listDisk.filter((item) => {
        return item.genre.toLowerCase().includes(this.details.toLowerCase())
      })
    },
  },
  methods: {
    getArray(){
      Axios
      .get(this.apiUrl)
      .then((result) =>{
        this.listDisk = result.data.response
        this.allGen();
      });
    },
    // funzione che ultilizzo per creare un array senza doppioni
    allGen(){
      for(let i = 0; i < this.listDisk.length; i++){
        if(!this.listGen.includes(this.listDisk[i].genre)){
          this.listGen.push(this.listDisk[i].genre)
        }
      }
    },
  }
};
</script>

<style scoped lang="scss">
  #container {
    margin: 0 auto;
    width: 60%;
    display: flex;
    flex-wrap: wrap;
    align-items: stretch;
    padding: 100px 0;
  }
</style>