

<script>
import AppMain from './components/Main.vue'
import AppHeader from './components/Header.vue'
export default {
  name: 'App',
  data () {
    return {
    

    }
  },
  components: {
    AppHeader,
    AppMain,

  },

}
</script>

<template>
  <AppHeader></AppHeader>
  <AppMain></AppMain>
  
</template>

<style lang="scss">
  @use './assets/app'
</style>