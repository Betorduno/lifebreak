<template>
  <div class="">
    <!-- Header Start -->
    <header id="home" class="position-relative ">
      <div v-if="imgs[index]">
        <div v-if="imgs[index].image.url" class="row mx-0 d-flex justify-content-center flex-row home-banner" :style="{ backgroundImage: `url(${imgs[index].image.url})` }">
          <div
            class="col-md-1 home-arrows "
            @click.stop="prev"
          >
            <svg
              class="arrows-g d-none d-md-block"
              fill="#fff"
              viewBox="0 0 24 24"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path d="M15.41 16.09l-4.58-4.59 4.58-4.59L14 5.5l-6 6 6 6z" />
              <path d="M0-.5h24v24H0z" fill="none" />
            </svg>
          </div>
          <div class="col-md-10">
            <div class="container hg">
              <div class="hero-area-wrapper d-flex flex-row wow fadeInLeft">
                <div class="line d-flex justify-content-center align-items-center align-content-center flex-column">
                  <div class="vertical mb-2"></div>
                  <div class="number-indice ">
                    <h2 class="text-center">{{index+1}}/{{vol}}</h2>
                  </div>
                </div>
                <div class="hero-area-content text-break">

                  <h3 class="subtitle position-relative">
                    <img class="img-ico" src="../../assets/img/home/lifebreak.svg" alt="">
                    {{ imgs[index].subtitle }}
                  </h3>
                  <h1 class="title text-break" data-aos="fade-right" data-aos-anchor="#example-anchor">{{ imgs[index].title }}</h1>
                  <br>
                  <p class="desc text-break" data-aos="fade-right">{{ imgs[index].desc }}</p>
                  <br>
                  <div class="hero-button-box py-2 py-md-5">
                    <span href="#" class="theme-btn" data-aos="fade-right">{{ imgs[index].textbtn }}</span>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div
            class="col-md-1 home-arrows "
            @click.stop="next"
          >
            <svg
              class="arrows-g d-none d-md-block"
              fill="#fff"
              viewBox="0 0 24 24"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path d="M8.59 16.34l4.58-4.59-4.58-4.59L10 5.75l6 6-6 6z" />
              <path d="M0-.25h24v24H0z" fill="none" />
            </svg>
          </div>
        </div>
        <div class="home-banner-rg" v-if="imgs[index].imagel.url" data-aos="fade-left" data-aos-offset="500" data-aos-duration="1500" :style="{ backgroundImage: `url(${imgs[index].imagel.url})` }"></div>
      </div>
      <div v-if="imgs[index]" class="circle text-white">
        <span v-if="imgs[index].image" class="px-1">
          <i :key="idx" v-for="(i ,idx) in imgs" :class="`fas fa-circle ${ idx == index ? 'active-color': ''}`"  @click.stop="changeSlider(idx)"></i>
        </span>
      </div>
    </header>
    <!-- Header End -->
  </div>
</template>

<script>
import { gql } from 'graphql-request';
export default {
  name: "Banner1",
  data() {
    return {
      index: 0,
      vol:0,
      imgs: [],
    };
  },

  methods: {
    async getData() {
    await this.$graphcms.request(
      gql`
        {
          bannerPrincipals {
            show
            title
            subtitle
            desc
            image {
              url
            }
            imagel {
              url
            }
            textbtn
            urlbtn
          }
        }
      `
    ).then((res)=>{
      this.imgs = res.bannerPrincipals;
      this.vol = this.imgs.length;
    });
  },
    changeSlider(id) {
      this.index = id;
    },
    prev() {
      if (this.index - 1 >= 0) {
        this.index -= 1;
      }
      else{
        this.index = this.imgs.length;
        this.index -= 1;
      }

    },
    next() {
      if (this.index === this.imgs.length-1) {
        this.index = 0;
      }
      else{
        this.index += 1;
      }
    },
    intervalTime(){
      setInterval(()=>{
        this.next();
      }, 10000);
    },
    onKeydown(e) {
      switch (e.key) {
        case "ArrowRight":
          this.next();
          break;
        case "ArrowLeft":
          this.prev();
          break;
        case "ArrowDown":
        case "ArrowUp":
        case " ":
          e.preventDefault();
          break;
      }
    }
  },
  mounted() {
    this.intervalTime();
    this.getData();
    document.addEventListener('aos', ({ detail }) => {
      console.log('animated in', detail);
    });
    window.addEventListener("keydown", this.onKeydown);
  },
  destroyed() {
    window.removeEventListener("keydown", this.onKeydown);
  }
};
</script>
<style lang="scss" scoped>

.line {
  display: block;
  margin-left: -4rem;
  margin-right: 8rem ;
  .vertical {
    display: block;
    background-color: #fff;
    width: 2px;
    height: 150px;
  }
  .number-indice h2 {
    display: block;
    z-index: 29;
    min-width: 37px;
    max-width: 37px;
    white-space: nowrap;
    font-size: 17px;
    line-height: 19px;
    font-weight: 700;
    color: rgb(255, 255, 255);
    letter-spacing: 0px;
    font-family: 'Mukta', sans-serif;
    visibility: inherit;
    transition: none 0s ease 0s;
    text-align: inherit;
    border-width: 0px;
    margin: 0px;
    padding: 0px;
    min-height: 29px;
    max-height: 29px;
    opacity: 1;
    transform: matrix3d(0, -1, 0, 0, 1, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1);
    transform-origin: 50% 50% 0px;
  }
}

.arrows-g {
  width: 60px;
}

.img-ico {
  width: 50px;
}

.subtitle {
    font-family: "Mukta",Sans-serif;
    color: #fff;
    font-size: 16px;
    font-weight: 400;
    text-transform: uppercase;
    line-height: 64px;
    letter-spacing: 1.6px;
  }

.title {
    font-family: "Mukta", sans-serif;
    z-index: 9;
    font-size: 86px;
    font-weight: 500;
    color: rgb(255, 255, 255);
    letter-spacing: -6px;
    font-family: 'Mukta', sans-serif;
    visibility: inherit;
    text-align: left;
    border-width: 0px;
    margin: 0px;
    padding: 0px;
    opacity: 1;
    white-space: initial;
}
.desc {
  z-index: 10;
  white-space: normal;
  font-size: 23px;
  line-height: 31px;
  font-weight: 300;
  color: rgb(255, 255, 255);
  font-family: Mukta;
  margin: 0px;
  padding: 0px;
  opacity: 1;
  white-space: initial;
}

.home-banner {
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  overflow: hidden;
  z-index: 1;
}

.hero-area-content {
  word-break: initial;
}

.home-banner-rg{
  display: block;
  position: absolute;
  right: 0;
  bottom: -80px;
  width: 50%;
  height: 80%;
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  overflow: hidden;
  z-index: 3;
}

.home-arrows {
  display: flex;
  align-content: center;
  align-items: center;
  justify-content: center;
  z-index: 100;
  line-height: 50px;
}

.circle {
  display: none;
}

@media(max-width: 1024px) {
  .title {
    font-size: 75px;
  }
  .line {
    display: none;
    .vertical {
      display: none;
    }
    .number-indice h2 {
      display: none;
    }
  }
}
@media(max-width: 768px) {
  .home-banner-rg {
    display: none;
  }

  .hg {
    min-height: 680px;
    max-height: 800px;
  }

  .circle {
    display: block;
    position: absolute;
    width: 100%;
    bottom: 1rem;
    text-align: center;
  }
  .circle span  i {
    color: #fff;
  }

  .active-color {
    color: #54a66a !important;
  }

  .arrows-g {
    width: 30px;
  }

  .title {
    font-size: 50px;
  }

  .line {
    display: none;
    margin-left: 0;
    margin-right: 0 ;
  }
}
</style>
