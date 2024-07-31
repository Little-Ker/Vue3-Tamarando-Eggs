<template>
    <div class="home">
        <!-- <img alt="Vue logo" src="../assets/logo.png" /> -->
        <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
        <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
        <Banner />
    </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Banner from '@/components/homeView/Banner.vue'

export default {
  name: 'HomeView',
  components: {
    // HelloWorld,
    Banner,
  },
}
</script>

<style lang="sass">
.home
  width: 100%


// nav
//   padding: 30px
//   a
//     font-weight: bold
//     color: #2c3e50
//     &.router-link-exact-active
//       color: #42b983
</style>



