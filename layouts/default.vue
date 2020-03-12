<template>
  <div>
    <Header />
    <main>
      <nuxt />
    </main>
    <Footer />
  </div>
</template>

<script>

import Header from '../components/Header'
import Footer from '../components/Footer'
export default {
  components: {
    Header,
    Footer
  }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css?family=Indie+Flower&display=swap');
  * {
    font-family: 'Indie Flower';
  }
  main {
    margin-top: 96px;
  }
</style>
