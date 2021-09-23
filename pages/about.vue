<template>
  <div class="home home-1" id="list-of-sections">
    <Header1/>
    <Banner title="Quienes Somos "/>
    <Learn/>
    <Testimonial :opinions="opt"/>
    <Tosubscribe/>
    <Footer/>
  </div>
</template>
<script>
import Header1 from '@/components/Header1.vue'
import Banner from '@/components/contacts/Banner.vue'
import Learn from '@/components/about/Learn.vue'
import Testimonial from '@/components/home1/Testimonial.vue'
import Tosubscribe from '@/components/home1/Tosubscribe.vue'
import Footer from '@/components/Footer.vue'

export default {
  components: {
    Header1,
    Banner,
    Learn,
    Testimonial,
    Tosubscribe,
    Footer
  },
  data() {
    return {
      opt: {
        title: 'Nuestro equipo',
        subtitle:'Quienes somos',
        desc: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam consectetur, leo quis mattis laoreet, mi odio malesuada ligula, eget bibendum lacus ligula sed mauris. Cras tincidunt justo eu dignissim faucibus. Sed eleifend neque a congue mattis. Duis dictum dolor non gravida tincidunt. Etiam cursus eros quis pretium suscipit. Sed pellentesque gravida est, rhoncus nibus turpis ornare nec. Aliquam vitae pharetra felis, a fringilla enim. ',
        boxs: [
          {
            title: 'COWORKING',
            image:'https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(117).jpg'
          },
          {
            title: 'SERVICIOS',
            image:'https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(117).jpg'
          },
          {
            title: 'ROOMS',
            image:'https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(117).jpg'
          }
        ],
        background: 'url(https://demo2wpopal.b-cdn.net/co-workshop/wp-content/uploads/2018/11/bgoc-1.png)'
      }
    }
  }
}
</script>