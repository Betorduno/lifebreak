<template>
  <div class="home home-1" id="list-of-sections">
    <Header1 />
    <Banner1 />
    <About/>
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
import Header1 from '@/components/Header1.vue'
import Banner1 from '@/components/home1/Banner1.vue'
import About from '@/components/home1/About.vue'
import Footer from '@/components/Footer.vue'

export default {
  components: {
    Header1,
    Banner1,
    About,
    Footer,
  }
}
</script>
