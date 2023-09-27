

<script>
import {store} from '../store.js'

export default {
    name: 'SearchImput',
    emits: ['performSearch'],
    data () {
    return {
        store,
    }
  },
  created() {
    store.fetchData();
  },

}
</script>
<template>
    <div class="py-3">
        <select class="form-select w-25" aria-label="Default select example" @change="$emit('performSearch')" v-model="store.selectArch">
            <option disabled value="">Choose Archetyp</option>
            <option value="Alien">Alien</option>
            <option value="Noble Knight">Noble Knight</option>
            <option value="Melodious">Melodious</option>
            <option value="Archfiend">Archfiend</option>
        </select>
    </div>
</template>

<style lang="scss" scoped></style>