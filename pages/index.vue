<template>
  <div class="home home-1" id="list-of-sections">
    <Header1/>
    <Banner1/>
    <About :abt="about"/>
    <Gallery :images="imgs"/>
    <Testimonial :opinions="opt"/>
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
  },
  data() {
    return {
      imgs: [
          'https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(117).jpg',
          'https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(98).jpg',
          'https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(131).jpg',
          'https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(123).jpg',
          'https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(118).jpg',
          'https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(128).jpg',
          'https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(132).jpg',
          'https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(115).jpg'
      ],
      about: {
        subtitle: 'ABOUT US',
        title: 'Community, creativity,<br>comfort & more',
        description: 'We are a community of bold minds who have decided to work under the same roof. Our workspace and the people around us inspire us to take action, to grow, to do better. By saying that our coworking space is sustainable and comfy we confirm that you will get 100% satisfaction from working here and making the best out of this experience.',
        textbtn: 'Leam more',
        urlbtn: '#',
      },
      opt: {
        title: 'People Talkings<br> About US',
        subtitle:'Testimonial',
        desc: '...una forma distinta de ver el trabajo, que intenta que este sea una parte integral del estilo de vida, y no compartimentos diferenciados de trabajo y ocio. En LifeBreak podrás trabajar cómodamente además de disfrutar de las instalaciones y las variadas actividades que ofrecemos. El propósito de nuestro coliving es crear un ambiente internacional y relaciones que vayan más allá de lo profesional, buscando interacciones de aprendizaje y colaboración entre los profesionales que lo habitan y los voluntarios internacionales que ayudan en el proyecto.',
        boxs: [
          {
            title: 'People Talking<br>About Us',
            image:'https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(117).jpg'
          },
          {
            title: 'People Talking<br>About Us',
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
