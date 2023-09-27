<script>
import {store} from '../store.js'
import Cards from './Cards.vue'



export default {
  name: 'AppMain',
  components: {
    Cards
  },
  data () {
    return {
        store,
    }
  },
  created() {
    store.fetchData();

  },
  methods: {
    searchArchetyp() {
        const url = 'https://db.ygoprodeck.com/api/v7/cardinfo.php' + '?archetype=Alien';
        console.log(store.fetchData);
    }
  }


}
</script>

<template>
    <main class="bg_orange">
        <div class="container w-75">
            <div class="py-3">
                <select class="form-select w-25" aria-label="Default select example" @change="searchArchetyp()">
                    <option selected>Choose Archetyp</option>
                    <option value="Alien">Alien</option>
                    <option value="Noble Knight">Noble Knight</option>
                    <option value="Tainted Treasure">Tainted Treasure</option>
                    <option value="Melodious">Melodious</option>
                    <option value="Archfiend">Archfiend</option>
                </select>
            </div>
            <div class="container bg-white p-5">
                <h4 class="m-auto bg-black text-white py-2">Found 39 cards</h4>
                <div class="bg-white container g-0">
                    <div class="row">
                        <Cards :card="card" v-for="card in store.cards" />
                    </div>


                </div>

                


            </div>

        </div>

    </main>
</template>

<style lang="scss" scoped>
.bg_orange {
    background-color: orange;
}

</style>