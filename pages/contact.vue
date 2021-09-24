<template>
  <div class="home home-1" id="list-of-sections">
    <Header1/>
    <Banner :data="contact"/>
    <Seccion/>
    <Infoperson/>
    <Form/>
    <Footer/>
  </div>
</template>

<script>
// @ is an alias to /src
import Header1 from '@/components/Header1.vue'
import Banner from '@/components/contacts/Banner.vue'
import Footer from '@/components/Footer.vue'
import Seccion from '@/components/contacts/Seccion.vue'
import Infoperson from '@/components/contacts/Infoperson.vue'
import Form from '@/components/contacts/Form.vue'
export default {
  components: {
    Header1,
    Banner,
    Seccion,
    Infoperson,
    Form,
    Footer
  },
  data() {
    return {
      contact:{
        title: 'Contáctenos',
        image: require('~/assets/img/contact/contactbanner.jpg')
      }
    }
  }
}
</script>