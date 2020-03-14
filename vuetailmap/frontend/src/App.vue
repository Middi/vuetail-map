<template>
  <div class="container bg-red-200" id="app">
        <!-- <h2 class="text-3xl">{{ home[0].title }}</h2>
        <img v-if="home[0].image" :src="'http://localhost:8000' + home[0].image.url" alt=""> -->
  </div>
</template>

<script>

// import './assets/styles/index.css';

export default {
  name: 'App',
  components: {
    
  },
  data () {
      return {
          home: []
      }
  },
  mounted () {
    fetch('http://localhost:8000/api/v2/pages/?type=home.HomePage&fields=body,image')
      .then(res => res.json())
      .then(res => this.home = res.items)
  }
}
</script>

<style>

</style>
