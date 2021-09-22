<template>
  <div class="home home-1" id="list-of-sections">
    <Header1/>
    <Banner1/>
    <About/>
    <Gallery/>
    <Testimonial/>
    <Services/>
    <Slidertestimonial/>
    <Tosubscribe/>
    <Footer/>
  </div>
</template>

<script>
// @ is an alias to /src
import Header1 from '@/components/Header1.vue'
import Banner1 from '@/components/home1/Banner1.vue'
import About from '@/components/home1/About.vue'
import Gallery from '@/components/home1/Gallery.vue'
import Testimonial from '@/components/home1/Testimonial.vue'
import Services from '@/components/home1/Services.vue'
import Slidertestimonial from '@/components/home1/Slidertestimonial.vue'
import Tosubscribe from '../components/home1/Tosubscribe.vue'
import Footer from '@/components/Footer.vue'



export default {
  components: {
    Header1,
    Banner1,
    About,
    Gallery,
    Testimonial,
    Services,
    Slidertestimonial,
    Tosubscribe,
    Footer
  }
}
</script>
