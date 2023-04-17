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
      API_URL: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=5&offset=0',
      cards: null
    }
  },
  methods: {
    callApi(url) {
      axios
        .get(url)
        .then(response => {
          console.log(response.data.data);
        })
        .catch(err => {
          console.error(err.message);
        })
    }
  },
  mounted() {
    this.callApi(this.API_URL);
  }
}
</script>

<template>
  <SiteHeader></SiteHeader>
  <!-- <SiteMain :cards="cards"></SiteMain> -->

  <div class="main">
    <select class="form-select select" aria-label="Default select example">
      <option selected>Alien</option>
      <option value="1">One</option>
      <option value="2">Two</option>
      <option value="3">Three</option>
    </select>
    <div class="card_box">
      <div class="result"></div>
      <div class="row d-flex justify-content-between">
        <div class="col-2 bg-black text-white" v-for="card in cards">
          <img src="card.data.images-card" alt="">
        </div>
      </div>
    </div>
  </div>
</template>

<style></style>
