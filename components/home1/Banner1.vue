<template>
  <div class="">
    <!-- Header Start -->

    <header id="home" class="position-relative ">
      <div v-if="imgs">
        <div v-if=" imgs[index]" class="row d-flex flex-nowrap justify-content-center flex-row home-banner" :style="`background-image: url('${ imgs[index].image}');`">
          <div
            class="col-md-1 home-arrows cursor-pointer px-5 d-flex align-content-center align-items-center justify-content-center flex-row"
            @click.stop="prev"
          >
            <svg
              class="pointer-events-none"
              fill="#fff"
              height="60"
              viewBox="0 0 24 24"
              width="60"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path d="M15.41 16.09l-4.58-4.59 4.58-4.59L14 5.5l-6 6 6 6z" />
              <path d="M0-.5h24v24H0z" fill="none" />
            </svg>
          </div>
          <div class="col-md-10">
            <div class="container">
              <div class="hero-area-wrapper wow fadeInLeft">
                <div class="hero-area-content ">
                  <h1 class="title" data-aos="fade-right">{{ imgs[index].title }}</h1>
                  <p class="subtitle" data-aos="fade-right">{{ imgs[index].subtitle }}</p>
                  <div class="hero-button-box">
                    <a href="#" class="theme-btn" data-aos="fade-right">{{ imgs[index].textbtn }}</a>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div
            class="col-md-1 home-arrows cursor-pointer px-5 d-flex align-content-center align-items-center justify-content-center"
            @click.stop="next"
          >
            <svg
              class="pointer-events-none"
              fill="#fff"
              height="60"
              viewBox="0 0 24 24"
              width="60"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path d="M8.59 16.34l4.58-4.59-4.58-4.59L10 5.75l6 6-6 6z" />
              <path d="M0-.25h24v24H0z" fill="none" />
            </svg>
          </div>
        </div>
        <div class="home-banner-rg" data-aos="fade-right"  :style="`background-image: url('${ imgs[index].imagel}');`"></div>
      </div>
    </header>
    <!-- Header End -->
  </div>
</template>

<script>
export default {
  name: "Banner1",
  data() {
    return {
      index: 0,
      imgs: [
        {
          title: "Lorem insup1 loreem daftesddf",
          subtitle: "..................",
          textbtn: "Schedule My Tour",
          urlbtn: "#",
          image:
            "https://demo2wpopal.b-cdn.net/co-workshop/wp-content/uploads/2018/11/leyer-h21.jpg",
          imagel:"https://demo2wpopal.b-cdn.net/co-workshop/wp-content/uploads/2018/11/leyer-h29.jpg"
        },
        {
          title: "Lorem insup2",
          subtitle: "..................",
          textbtn: "Schedule My Tour",
          urlbtn: "#",
          image:
            "https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(98).jpg",
          imagel:"https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(98).jpg"
        },
        {
          title: "Lorem insup3",
          subtitle: "..................",
          textbtn: "Schedule My Tour",
          urlbtn: "#",
          image:
            "https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(131).jpg",
          imagel:"https://demo2wpopal.b-cdn.net/co-workshop/wp-content/uploads/2018/11/leyer-h29.jpg"
        },
        {
          title: "Lorem insup4",
          subtitle: "..................",
          textbtn: "Schedule My Tour",
          urlbtn: "#",
          image:
            "https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(123).jpg",
          imagel:"https://demo2wpopal.b-cdn.net/co-workshop/wp-content/uploads/2018/11/leyer-h29.jpg"
        },
        {
          title: "Lorem insup5",
          subtitle: "..................",
          textbtn: "Schedule My Tour",
          urlbtn: "#",
          image:
            "https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(118).jpg",
          imagel:"https://demo2wpopal.b-cdn.net/co-workshop/wp-content/uploads/2018/11/leyer-h29.jpg"
        },
        {
          title: "Lorem insup6",
          subtitle: "..................",
          textbtn: "Schedule My Tour",
          urlbtn: "#",
          image:
            "https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(128).jpg",
          imagel:"https://demo2wpopal.b-cdn.net/co-workshop/wp-content/uploads/2018/11/leyer-h29.jpg"
        },
        {
          title: "Lorem insup7",
          subtitle: "..................",
          textbtn: "Schedule My Tour",
          urlbtn: "#",
          image:
            "https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(132).jpg",
          imagel:"https://demo2wpopal.b-cdn.net/co-workshop/wp-content/uploads/2018/11/leyer-h29.jpg"
        },
        {
          title: "Lorem insup8",
          subtitle: "..................",
          textbtn: "Schedule My Tour",
          urlbtn: "#",
          image:
            "https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(115).jpg",
          imagel:"https://demo2wpopal.b-cdn.net/co-workshop/wp-content/uploads/2018/11/leyer-h29.jpg"
        }
      ]
    };
  },
  methods: {
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
      }, 15000);
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
    // this.intervalTime();
    window.addEventListener("keydown", this.onKeydown);
  },
  destroyed() {
    window.removeEventListener("keydown", this.onKeydown);
  }
};
</script>
<style lang="scss" scoped>

.title {
    font-family: "Mukta", sans-serif;
    z-index: 9;
    min-width: 678px;
    max-width: 678px;
    white-space: nowrap;
    font-size: 105px;
    line-height: 105px;
    font-weight: 500;
    color: rgb(255, 255, 255);
    letter-spacing: -6px;
    font-family: 'Mukta', sans-serif;
    visibility: inherit;
    transition: none 0s ease 0s;
    text-align: left;
    border-width: 0px;
    margin: 0px;
    padding: 0px;
    min-height: 0px;
    max-height: none;
    opacity: 1;
    transform: matrix3d(1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1);
    transform-origin: 50% 50% 0px;
    white-space: initial;
}
.subtitle {
  z-index: 10;
  min-width: 454px;
  max-width: 454px;
  white-space: normal;
  font-size: 23px;
  line-height: 31px;
  font-weight: 300;
  color: rgb(255, 255, 255);
  letter-spacing: 0px;
  font-family: Mukta;
  visibility: inherit;
  transition: none 0s ease 0s;
  text-align: inherit;
  border-width: 0px;
  margin: 0px;
  padding: 0px;
  min-height: 66px;
  max-height: 66px;
  opacity: 1;
  transform: matrix3d(1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1);
  transform-origin: 50% 50% 0px;
  white-space: initial;
}

.home-banner {
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  overflow: hidden;
  z-index: 1;
}

.home-banner-rg{
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
  z-index: 100;
  line-height: 50px;;
}
</style>
