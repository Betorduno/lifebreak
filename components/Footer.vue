<template>
  <div>
    <!-- Footer Start -->
    <footer class="copyrightarea">
        <div class="">
            <div class="row d-flex justify-content-center">
                <img class="logo" src="https://demo2wpopal.b-cdn.net/co-workshop/wp-content/uploads/2018/11/logo_02.png" alt="">
            </div>
            <div class="row my-5 justify-content-center p-md-5 p-xs-2">
                <div class="col-xs-12 col-md-2 text-center">
                    <nuxt-link to="#" class="links">Inicio</nuxt-link>
                </div>
                <div class="col-xs-12 col-md-2  text-center">
                    <nuxt-link to="#" class="links">Programa Ingles</nuxt-link>
                </div>
                <div class="col-xs-12 col-md-2  text-center">
                    <nuxt-link to="#" class="links">Blog</nuxt-link>
                </div>
                <div class="col-xs-12 col-md-2  text-center">
                    <nuxt-link to="#" class="links">Contacto</nuxt-link>
                </div>
            </div>
            <div class="row flex-nowrap align-items-center align-content-center content">
                <div class="col-md-5">
                    <div class="divisor"></div>
                </div>
                <div class="col-md-2">
                    <div class="row f d-flex flex-nowrap justify-content-center align-items-center align-content-center">
                        <div class="col-2 text-center">
                            <i class="fab fa-google-plus"></i>
                        </div>
                        <div class="col-2 text-center">
                            <i class="fab fa-facebook"></i>
                        </div>
                        <div class="col-2 text-center">
                            <i class="fab fa-twitter"></i>
                        </div>
                        <div class="col-2 text-center">
                            <i class="fab fa-youtube"></i>
                        </div>

                    </div>
                </div>
                <div class="col-md-5">
                    <div class="divisor"></div>
                </div>
            </div>
            <div class="row justify-content-center mt-5">
                <p class="text-white">Copyright © 2021 - Madatto&Mosscreativo</p>
            </div>
        </div>
    </footer>
    <!-- Footer End -->
  </div>
</template>

<script>

export default {
  name: 'Footer',
}
</script>
<style scoped>
    .copyrightarea {
        background-color: #1e3954;
        background-image: url(https://demo2wpopal.b-cdn.net/co-workshop/wp-content/uploads/2018/11/elipse.png);
        background-position: bottom left;
        background-repeat: no-repeat;
        padding: 120px 0;
    }

    .logo {
        width: 18rem;
    }
     .links {
       font-size: 24px;
       font-weight: 400;
       color: #fff;
     }
    .divisor {
        border-top: 1px solid rgba(255,255,255,.2);
        width:100%
    }
    .content {
        margin-top: 6rem;
    }

    i {
        color: #949ca6;
        font-size: 20px;
    }

</style>