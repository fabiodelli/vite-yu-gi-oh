<script>
import axios from 'axios'
import SiteHeader from './components/SiteHeader.vue'
import SiteMain from './components/SiteMain.vue'

export default {
  components: {
    SiteHeader,
    SiteMain,
  },
  data() {
    return {
      API_URL: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=200&offset=0',
      
      cards: null
    }
  },
  methods: {
    
    callApi(url) {
      axios
        .get(url+'archetype={{siteMain.search}}')
        .then(response => { 
          this.cards = response.data.data
        })
        .catch(err => {
          console.error(err.message);
        })
        console.log(SiteMain.search);
    }
  },
  mounted() {
    this.callApi(this.API_URL);
  }
}
</script>

<template>

  <SiteHeader></SiteHeader>

  <SiteMain :cards="cards" @changed="callApi()"></SiteMain>
 
</template>

<style></style>
