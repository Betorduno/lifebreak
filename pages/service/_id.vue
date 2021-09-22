<template>
  <div class="home home-1" id="list-of-sections">
    <Header1/>
    <Footer/>
  </div>
</template>
<script>
import Header1 from '@/components/Header1.vue'
import Footer from '@/components/Footer.vue'
export default {
  components: {
    Header1,
    Footer
  }
}
</script>