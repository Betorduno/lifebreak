<template>
  <div>
    <client-only>
    <!-- Footer Start -->
    <footer class="copyrightarea">
        <div class="">
            <div class="row m-0 d-flex justify-content-center">
                <img class="logo mb-5" src="../assets/img/logo.svg" alt="">
            </div>
            <div class="row m-0 flex-nowrap align-items-center align-content-center content">
                <div class="col-md-5">
                    <div class="divisor"></div>
                </div>
                <div class="col-md-2">
                    <div class="row f d-flex flex-nowrap justify-content-center align-items-center align-content-center">
                        <div class="col-2 text-center">
                            <a target="blank" href="https://instagram.com/lifebreak_guatape?utm_medium=copy_link"><i class="fab fa-instagram"></i></a>
                        </div>
                        <div class="col-2 text-center">
                            <a target="blank" href="https://www.facebook.com/Lifebreak_Guatape-100609869056515"><i class="fab fa-facebook"></i></a>
                        </div>
                        <div class="col-2 text-center">
                            <a target="blank" href="#"><i class="fab fa-youtube"></i></a>
                        </div>

                    </div>
                </div>
                <div class="col-md-5">
                    <div class="divisor"></div>
                </div>
            </div>
            <div class="row m-0 justify-content-center mt-5">
                <p class="text-white text-center">Copyright © 2021 - Madatto&MOSScreativo</p>
            </div>
        </div>
    </footer>
    </client-only>
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
        background-color: #428a70;
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
        border-top: 1px solid #ffffff80;
        width:100%
    }
    .content {
        margin-top: 6rem;
    }

    i {
        color: #fff;
        font-size: 20px;
    }

</style>