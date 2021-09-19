<template>
  <div class="">
    <!-- Header Start -->
    <header id="home" class="home-banner-area position-relative">

        <div class="container">
            <div class="row">
                <div class="col-12">
                    <!--Hero Area Wrapper-->
                    <div class="hero-area-wrapper position-relative wow fadeInLeft">
                        <div class="hero-area-content">
                            <h1 class="title">{{ heroTitle }}</h1>
                            <p class='subtitle'>{{heroSubTitle}}</p>
                            <div class="hero-button-box">
                                <a href="#" class="theme-btn">Schedule My Tour</a>
                            </div>
                        </div>
                    </div>
                    <!--Hero Area Wrapper-->
                </div>
            </div>
        </div>
    </header>
    <!-- Header End -->
  </div>
</template>

<script>
export default {
  name: 'Banner1',

  data(){
    return {
      particleImage: require('../../assets/img/hero-bg-effect.png'),
      altText: 'particle',
      heroTitle: 'Creative space',
      heroSubTitle: 'Whether it’s working for yourself, or remotely,it’s great to be independent.'
    }
  }

}
</script>
<style >
  .title {
    font-family: 'Mukta', sans-serif;
    font-size: 60px;
  }

</style>
