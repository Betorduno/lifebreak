<template>
  <div>
    <Header1/>
    <Banner :data="banner"/>
    <Ourbenefits :ourbenefit="benefits"/>
    <Offer :offeri="offeri"/>
    <Gallery :objimg="gallery"/>
    <About :abt="about"/>
    <Testimonial :opinions="opt"/>
    <Footer/>
  </div>
</template>
<script>
import Header1 from '@/components/Header1.vue'
import Banner from '@/components/contacts/Banner.vue'
import Ourbenefits from '@/components/service/Ourbenefits.vue'
import Offer from '@/components/service/Offer.vue'
import Gallery from '@/components/home1/Gallery.vue'
import About from '../../components/home1/About.vue'
import Testimonial from '@/components/home1/Testimonial.vue'
import Footer from '@/components/Footer.vue'
import { gql } from 'graphql-request';

export default {
  components: {
    Header1,
    Banner,
    Ourbenefits,
    Offer,
    Gallery,
    About,
    Testimonial,
    Footer,

  },
  data() {
    return {
      service: {},
      banner: {},
      benefits:{},
      offeri: {},
      imgs: {},
      gallery: {},
      about: {},
      opt: {},
    }
  },
   created() {
    this.fetchData();
  },
  watch: {
    $route: 'fetchData',
  },
  methods: {
    async fetchData() {
      this.service = null
      try {
        const data = await this.$graphcms.request(
          gql`
            query getServicios($id: ID!) {
              servicios(where: { id: $id }) {
                id
                englishProgram
                titlebanner
                imagebanner {
                  url
                }
                subtitlebenefit
                titlebenefit
                descbenefit
                listbenefit
                tetxbtnbenefits
                urlDelBotonBeneficio
                imagebenefit {
                  url
                }
                titleoffer
                subtituloOferta
                descoffer
                listaOfertas {
                  title
                  desc
                  image {
                    url
                  }
                }
                galerias {
                  imagemain {
                    url
                  }
                  galleryimage {
                    url
                  }
                }
                titleabout
                subtitleabout
                descabout
                textbtnabout
                urlbtnabout
                titleperson
                subtitleperson
                descperson
                boxperson {
                  ... on CajasDeInformacion {
                    id
                    title
                    image {
                      url
                    }
                  }
                }
              }
            }
          `,
          {
            id: this.$route.params.id,
          }
        );
        this.service=data.servicios;
        this.banner = {
          title: this.service.titlebanner,
          image: this.service.imagebanner.url
        }
        this.benefits = {
          title: this.service.titlebenefit,
          subtitle:this.service.subtitlebenefit,
          desc: this.service.descbenefit,
          list: this.service.listbenefit,
          textbtn: this.service.tetxbtnbenefits,
          urlbtn: this.service.urlDelBotonBeneficio,
          image: this.service.imagebenefit.url
        }

        this.offeri = {
          title: this.service.titleoffer,
          subtitle: this.service.subtituloOferta,
          desc: this.service.descoffer,
          gallery: this.service.listaOfertas
        }

        this.gallery = this.service.galerias;

        this.about= {
          subtitle: this.service.subtitleabout,
          title: this.service.titleabout,
          description: this.service.descabout,
          textbtn: this.service.textbtnabout,
          urlbtn: this.service.urlbtnabout,
        }

        this.opt = {
          title: this.service.titleperson,
          subtitle:this.service.subtitleperson,
          desc: this.service.descperson,
          boxs: this.service.boxperson,
        }
      } catch (e) {
        // handle error
        console.log('hola')
        window.location.href="/"
      }
    },
  },
}
</script>