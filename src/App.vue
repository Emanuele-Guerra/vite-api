<script>
  import AppCard from "./components/AppCard.vue"
  
  import axios from 'axios';
  
  
  export default{
    components: {
      
      AppCard

    },
    data() {
        return{
          pubs: []
        }
      },
  
  methods: {
    getBeer() {

      axios.get('https://api.openbrewerydb.org/v1/breweries?by_country=austria&per_page=10').then(risultato =>{
        this.pubs.push(...risultato.data)
        console.log(this.pubs)
          
          
      })
    }
  },
  mounted(){
    this.getBeer();
  }
};
  
  
 
</script>

<template>
    <AppCard :arrayGenerato="pubs" />
</template>

<style scoped>
</style>
