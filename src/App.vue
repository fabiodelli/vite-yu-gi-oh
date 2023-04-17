<script>
import axios from 'axios'
import SiteHeader from './components/SiteHeader.vue'
import SiteMain from './components/SiteMain.vue'

export default {
  components:{
    SiteHeader,
    SiteMain,
  },
  data() {
    return {
      API_URL:'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=5&offset=0',
      cards:null
    }
  },
  methods: {
    callApi(url){
      axios
      .get(url)
      .then(response =>{
        console.log(response.data.data[0].card_images);
      })
      .catch(err => {
        console.error(err.message);
      })
    }
  },
  mounted(){
    this.callApi(this.API_URL);
  }
}
</script>

<template>

  <SiteHeader></SiteHeader>
  <SiteMain :cards="cards"></SiteMain>

</template>

<style>
</style>
