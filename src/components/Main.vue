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
      console.log(this.card_sets);
    })
  }


}
</script>

<template>
    <main class="bg_orange">
        <div class="container w-75">
            <div class="py-3">
                <select class="form-select w-25" aria-label="Default select example">
                    <option selected>Alien</option>
                    <option value="1">One</option>
                    <option value="2">Two</option>
                    <option value="3">Three</option>
                </select>
            </div>
            <div class="container bg-white p-5">
                <h4 class="m-auto bg-black text-white py-2">Found 39 cards</h4>
                <div class="bg_orange container g-0">
                    <div class="row g-0">
                        <div class="col-3">
                            <img :src="card_sets[0].card_images[0].image_url" alt="">
                        </div>
                    </div>


                </div>

                


            </div>

        </div>

    </main>
</template>

<style lang="scss" scoped>
.bg_orange {
    background-color: orange;
    height: 600px;
}

</style>