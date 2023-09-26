

<script>
import AppMain from './components/Main.vue'
import AppHeader from './components/Header.vue'
import axios from 'axios'
export default {
  name: 'App',
  data () {
    return {
      base_url: 'https://db.ygoprodeck.com/api/v7/cardinfo.php',
      card_sets: null,
      card_images: null,

    }
  },
  components: {
    AppHeader,
    AppMain,

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
  <AppHeader></AppHeader>
  <AppMain></AppMain>
  
</template>

<style lang="scss" scoped>

</style>