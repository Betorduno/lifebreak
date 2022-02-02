<template>
  <div class="home home-1" id="list-of-sections">
    <Header1/>
    <Banner1/>
    <About :abt="about"/>
    <Gallery :objimg="imgs"/>
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
          {
            imagemain: {url: require('@/assets/img/galeria/01.jpg')},
            galleryimage: [
              { url: require('@/assets/img/galeria/01.jpg')},
              { url: require('@/assets/img/galeria/02.jpg')},
              { url: require('@/assets/img/galeria/03.jpg')},
              { url: require('@/assets/img/galeria/04.jpg')},
              { url: require('@/assets/img/galeria/05.jpg')},
              { url: require('@/assets/img/galeria/06.jpg')},
              { url: require('@/assets/img/galeria/07.jpg')},
              { url: require('@/assets/img/galeria/08.jpg')},
              { url: require('@/assets/img/galeria/09.jpg')},
              { url: require('@/assets/img/galeria/10.jpg')},
              { url: require('@/assets/img/galeria/11.jpg')},
              { url: require('@/assets/img/galeria/12.jpg')},
              { url: require('@/assets/img/galeria/13.jpg')},
              { url: require('@/assets/img/galeria/14.jpg')},
            ]
          },
          {
            imagemain: {url: require('@/assets/img/galeria/02.jpg')},
            galleryimage: [
              { url: require('@/assets/img/galeria/01.jpg')},
              { url: require('@/assets/img/galeria/02.jpg')},
              { url: require('@/assets/img/galeria/03.jpg')},
              { url: require('@/assets/img/galeria/04.jpg')},
              { url: require('@/assets/img/galeria/05.jpg')},
              { url: require('@/assets/img/galeria/06.jpg')},
              { url: require('@/assets/img/galeria/07.jpg')},
              { url: require('@/assets/img/galeria/08.jpg')},
              { url: require('@/assets/img/galeria/09.jpg')},
              { url: require('@/assets/img/galeria/10.jpg')},
              { url: require('@/assets/img/galeria/11.jpg')},
              { url: require('@/assets/img/galeria/12.jpg')},
              { url: require('@/assets/img/galeria/13.jpg')},
              { url: require('@/assets/img/galeria/14.jpg')},
            ]
          },
          {
            imagemain: {url: require('@/assets/img/galeria/03.jpg')},
            galleryimage: [
              { url: require('@/assets/img/galeria/01.jpg')},
              { url: require('@/assets/img/galeria/02.jpg')},
              { url: require('@/assets/img/galeria/03.jpg')},
              { url: require('@/assets/img/galeria/04.jpg')},
              { url: require('@/assets/img/galeria/05.jpg')},
              { url: require('@/assets/img/galeria/06.jpg')},
              { url: require('@/assets/img/galeria/07.jpg')},
              { url: require('@/assets/img/galeria/08.jpg')},
              { url: require('@/assets/img/galeria/09.jpg')},
              { url: require('@/assets/img/galeria/10.jpg')},
              { url: require('@/assets/img/galeria/11.jpg')},
              { url: require('@/assets/img/galeria/12.jpg')},
              { url: require('@/assets/img/galeria/13.jpg')},
              { url: require('@/assets/img/galeria/14.jpg')},
            ]
          },
          {
            imagemain: {url: require('@/assets/img/galeria/04.jpg')},
            galleryimage: [
              { url: require('@/assets/img/galeria/01.jpg')},
              { url: require('@/assets/img/galeria/02.jpg')},
              { url: require('@/assets/img/galeria/03.jpg')},
              { url: require('@/assets/img/galeria/04.jpg')},
              { url: require('@/assets/img/galeria/05.jpg')},
              { url: require('@/assets/img/galeria/06.jpg')},
              { url: require('@/assets/img/galeria/07.jpg')},
              { url: require('@/assets/img/galeria/08.jpg')},
              { url: require('@/assets/img/galeria/09.jpg')},
              { url: require('@/assets/img/galeria/10.jpg')},
              { url: require('@/assets/img/galeria/11.jpg')},
              { url: require('@/assets/img/galeria/12.jpg')},
              { url: require('@/assets/img/galeria/13.jpg')},
              { url: require('@/assets/img/galeria/14.jpg')},
            ]
          },
          {
            imagemain: {url: require('@/assets/img/galeria/05.jpg')},
            galleryimage: [
              { url: require('@/assets/img/galeria/01.jpg')},
              { url: require('@/assets/img/galeria/02.jpg')},
              { url: require('@/assets/img/galeria/03.jpg')},
              { url: require('@/assets/img/galeria/04.jpg')},
              { url: require('@/assets/img/galeria/05.jpg')},
              { url: require('@/assets/img/galeria/06.jpg')},
              { url: require('@/assets/img/galeria/07.jpg')},
              { url: require('@/assets/img/galeria/08.jpg')},
              { url: require('@/assets/img/galeria/09.jpg')},
              { url: require('@/assets/img/galeria/10.jpg')},
              { url: require('@/assets/img/galeria/11.jpg')},
              { url: require('@/assets/img/galeria/12.jpg')},
              { url: require('@/assets/img/galeria/13.jpg')},
              { url: require('@/assets/img/galeria/14.jpg')},
            ]
          },
          {
            imagemain: {url: require('@/assets/img/galeria/06.jpg')},
            galleryimage: [
              { url: require('@/assets/img/galeria/01.jpg')},
              { url: require('@/assets/img/galeria/02.jpg')},
              { url: require('@/assets/img/galeria/03.jpg')},
              { url: require('@/assets/img/galeria/04.jpg')},
              { url: require('@/assets/img/galeria/05.jpg')},
              { url: require('@/assets/img/galeria/06.jpg')},
              { url: require('@/assets/img/galeria/07.jpg')},
              { url: require('@/assets/img/galeria/08.jpg')},
              { url: require('@/assets/img/galeria/09.jpg')},
              { url: require('@/assets/img/galeria/10.jpg')},
              { url: require('@/assets/img/galeria/11.jpg')},
              { url: require('@/assets/img/galeria/12.jpg')},
              { url: require('@/assets/img/galeria/13.jpg')},
              { url: require('@/assets/img/galeria/14.jpg')},
            ]
          }
      ],
      about: {
        subtitle: 'PROGRAMA INGLÉS',
        title: 'Are you ready <br>to improve?',
        description: 'Es el momento de mejorar tu nivel de inglés para  dar un impulso a tu carrera profesional y a tu apertura al mundo!',
        textbtn: 'Programa Ingles',
        urlbtn: '#',
      },
      opt: {
        title: 'Un espacio de<br>“coliving”',
        subtitle:'QUÉ OFRECEMOS',
        desc: 'Una forma distinta de ver el trabajo en la que este se considera como parte integral del estilo de vida, y no como un compartimento diferenciado al ocio.<br><br> En LifeBreak podrás trabajar cómodamente además de disfrutar de las instalaciones y las variadas actividades que ofrecemos.<br><br> El propósito de nuestro coliving es crear un ambiente internacional y relaciones que vayan más allá de lo profesional, buscando interacciones de aprendizaje y colaboración entre los profesionales que lo habitan y los voluntarios internacionales que ayudan en el proyecto.',
        boxs: [
          {
            title: 'COWORKING',
            image:{ url: require('@/assets/img/home/s1.jpg')}
          },
          {
            title: 'SERVICIOS',
            image: { url: require('@/assets/img/home/s2.jpg')}
          },
          {
            title: 'ROOMS',
            image: { url: require('@/assets/img/home/s3.jpg')}
          }
        ],
        background: 'url(https://demo2wpopal.b-cdn.net/co-workshop/wp-content/uploads/2018/11/bgoc-1.png)'
      }
    }
  }
}
</script>
