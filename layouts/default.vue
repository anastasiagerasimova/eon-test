<template>
  <div>
    <vue-header></vue-header>

    <main>
      <div class="container">
        <Nuxt />
      </div>
    </main>
    
  </div>
</template>

<script>
import VueHeader from '@/components/VueHeader'

export default {
    components: {
        VueHeader
    }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@100;200;400;500;600;700;800;900&display=swap');
  * {
    box-sizing: border-box;
  }

  body {
    font-family: 'Inter', sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    font-size: 16px;
    color: #2c3e50;
    /* background: #2c3e50; */
    margin: 0;
  }
  .container {
  margin: 0 auto;
  max-width: 1170px;
  /* background-color: #e53935; */
  }
</style>
