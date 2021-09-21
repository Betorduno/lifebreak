<template>
  <div class="container-fluid">
    <div class="row bg-dark">
      <div class="col-md-3 col-sm-6 col-xs-12 single_portfolio_text" :key="idx" v-for="(img, idx) in imgs">
        <img :src="img" alt="" />
        <div class="portfolio_images_overlay text-center">
          <Box thumbnail="img" :images="imgs" :idx=idx>
            <template v-slot:image>
              <h6 class="clrd-font">View Gallery</h6>
            </template>
          </Box>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Lightbox from '@/components/home1/Lightbox.vue'
  export default {
    components: {
      Box: Lightbox
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
      };
    }
  }
</script>

<style scoped>
* {
  padding: 0;
  margin: 0;
  -webkit-transition: 1s;
  transition: 1s;
}

.single_portfolio_text {
  display: inline-block;
  padding: 0;
  position: relative;
  overflow: hidden;
}
.single_portfolio_text img {
  width: 100%;
}

#silentImg img {
  width: 100%;
}

.single_portfolio_text:hover .portfolio_images_overlay {
  top: 0%;
  left: 0%;
}

.portfolio_images_overlay {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.8);
  padding: 20px;
  margin: 0 auto;
  top: -100%;
  left: 5%;
  position: absolute;
  display: flex;
  align-content: center;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  transition: 0.6s;
}
.portfolio_images_overlay h6 {
  text-transform: uppercase;
  color: #fff;
  font-size: 1.77rem;
  font-weight: 900;
  padding-top: 10px;
  padding-bottom: 10px;
}

.portfolio_images_overlay .product_price {
  font-size: 35px;
  color: #fff;
  font-weight: 800;
  line-height: 30px;
}
.portfolio_images_overlay .product_price i {
  margin-right: -10px;
}

@media (min-width: 769px) and (max-width: 991px) {
  .portfolio_images_overlay {
    padding: 0px;
  }
}
@media (max-width: 768px) {
  .portfolio_images_overlay {
    padding: 170px 20px;
  }
}
@media (max-width: 580px) {
  .portfolio_images_overlay {
    padding: 100px 20px;
  }
}
@media (max-width: 480px) {
  .portfolio_images_overlay {
    padding: 40px 20px;
  }
}
@media (max-width: 320px) {
  .portfolio_images_overlay {
    padding: 20px;
  }
}
</style>