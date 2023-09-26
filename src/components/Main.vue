<script>
import {store} from '../store.js'
import axios from 'axios'



export default {
  name: 'AppMain',
  data () {
    return {
        store,
        base_url: 'https://db.ygoprodeck.com/api/v7/cardinfo.php',
        card_sets: null,
        card_images: null,
    }
  },
  created() {
    axios
    .get(this.base_url)
    .then(response => {
      console.log(response.data.data[0].card_images[0].image_url);
      this.card_sets = response.data.data
    })
  }


}
</script>

<template>
</template>

<style lang="scss" scoped>

</style>