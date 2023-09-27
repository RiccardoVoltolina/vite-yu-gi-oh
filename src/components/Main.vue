<script>
import {store} from '../store.js'
import Cards from './Cards.vue'
import SearchImput from './SearchImput.vue'



export default {
  name: 'AppMain',
  components: {
    Cards,
    SearchImput,
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
/*         this.store.base_url = 'https://db.ygoprodeck.com/api/v7/cardinfo.php' + `?archetype=${}`;
 */        console.log(store.selectArch);
    }
  }


}
</script>

<template>
    <main class="bg_orange">
        <div class="container w-75">
            <SearchImput @performSearch="searchArchetyp()"/>
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