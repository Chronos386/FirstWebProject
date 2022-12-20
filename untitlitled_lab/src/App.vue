<template>
  <div id="app">
    <section class="wrapper">
      <Header/>
      <main class="container">
        <router-view/>
      </main>
    </section>
    <Footer/>
  </div>
</template>

<script>
import Header from '@/components/Main/Header'
import Footer from '@/components/Main/Footer'
export default {
  components: {
    Header,
    Footer
  }
}
</script>

<style lang="scss">
  body {
    background: url(assets/beer.jpeg);
  }

  .container {
    margin: 0 auto;
    padding: 0 15px;
    max-width: 1200px;
  }

  * {
    margin: 0;
    padding: 0;
  }

  .wrapper {
    min-height: 100vh;
    margin-bottom: 30px;
  }
</style>
