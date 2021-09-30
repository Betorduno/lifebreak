<template>
  <div>
    <!--Main Menu/ Mobile Menu Section-->
    <section class="menu-section-area">
      <!-- Navigation -->
      <b-navbar
        v-b-scrollspy:list-of-sections
        v-b-scrollspy="20"
        class="
          navbar navbar-expand-lg
          fixed-top
          d-none d-sm-none d-md-block d-lg-block d-xl-block
        "
        id="mainNav"
      >
        <div class="container">
          <nuxt-link class="navbar-brand js-scroll-trigger" to="/">
            <b-img
              :src="require('../assets/img/logo.png')"
              img-alt="RATH Logo"
              class="img-fluid logo"
            ></b-img>
          </nuxt-link>
          <button
            class="navbar-toggler navbar-toggler-right"
            type="button"
            data-toggle="collapse"
            data-target="#navbarResponsive"
            aria-expanded="false"
            aria-label="Toggle navigation"
          >
            <i class="fas fa-bars"></i>
          </button>
          <div class="collapse navbar-collapse" id="navbarResponsive">
            <ul class="navbar-nav text-capitalize ml-auto">
              <li class="nav-item">
                <a class="nav-link js-scroll-trigger" href="/" target="_self"
                  >INICIO</a
                >
              </li>
              <li class="nav-item dropdown">
                <a
                  href="#"
                  class="nav-link js-scroll-trigger dropdown-toggle"
                  data-toggle="dropdown"
                  >PROGRAMA INGLÉS<i class="fas fa-angle-down"></i
                ></a>
                <ul class="dropdown-menu">
                  <li  :key="idx"  v-for="(link, idx) in links"><nuxt-link v-if="link.englishProgram === true" :to="`/english/${link.id}`">{{link.titleLink}}</nuxt-link></li>
                </ul>
              </li>

              <li class="nav-item dropdown">
                <a
                  href="#"
                  class="nav-link js-scroll-trigger dropdown-toggle"
                  data-toggle="dropdown"
                  >QUE OFRECEMOS<i class="fas fa-angle-down"></i
                ></a>
                <ul class="dropdown-menu">
                  <li  :key="idx"  v-for="(link, idx) in links"><nuxt-link v-if="link.englishProgram === false" :to="`/english/${link.id}`">{{link.titleLink}}</nuxt-link></li>
                </ul>
              </li>

              <li class="nav-item">
                <nuxt-link to="/about" class="nav-link js-scroll-trigger"
                  >QUIENES SOMOS</nuxt-link
                >
              </li>
              <li class="nav-item">
                <nuxt-link to="/blog" class="nav-link js-scroll-trigger"
                  >BLOG</nuxt-link
                >
              </li>
              <li class="nav-item">
                <nuxt-link to="/contact" class="nav-link js-scroll-trigger m-0"
                  >CONTÁCTENOS</nuxt-link
                >
              </li>
            </ul>
          </div>
        </div>
      </b-navbar>
      <!-- Navigation -->

      <!-- Mobile Menu Start -->
      <b-navbar
        toggleable="lg"
        v-b-scrollspy:list-of-sections
        v-b-scrollspy="20"
        class="mobile_menu fixed-top hidden d-none"
        id="mainNavMobile"
      >
        <b-container fluid>
          <b-navbar-brand to="/"
            ><b-img
              :src="require('../assets/img/logo.png')"
              img-alt="RATH Logo"
              class="ml-4 ml-sm-4 ml-md-0 mobile-logo"
            ></b-img
          ></b-navbar-brand>

          <b-navbar-toggle class="mr-4 mr-sm-4 mr-md-0" target="nav-collapse">
            <template v-slot:default="{ expanded }">
              <b-icon v-if="expanded" icon="x"></b-icon>
              <b-icon v-else icon="list"></b-icon>
            </template>
          </b-navbar-toggle>

          <b-collapse id="nav-collapse" is-nav>
            <!-- Right aligned nav items -->
            <b-navbar-nav class="ml-auto">
              <b-nav-item href="#about">INICIO</b-nav-item>
              <b-nav-item-dropdown
                to="#"
                text="PROGRAMA INGLES"
                no-caret
                class="fas fa-angle-down"
              >
                <b-dropdown-item v-if="link.englishProgram === true" :key="idx"  v-for="(link, idx) in links" :to="`/english/${link.id}`">{{link.titleLink}}</b-dropdown-item>

              </b-nav-item-dropdown>
              <b-nav-item-dropdown
                to="#"
                text="QUE OFRECEMOS"
                no-caret
                class="fas fa-angle-down"
              >
                <b-dropdown-item v-if="link.englishProgram === false" :key="idx"  v-for="(link, idx) in links" :to="`/english/${link.id}`">{{link.titleLink}}</b-dropdown-item>
              </b-nav-item-dropdown>

              <b-nav-item href="#screenshots">QUIENES SOMOS</b-nav-item>
              <b-nav-item href="#features">BLOG</b-nav-item>
              <b-nav-item href="#reviews">CONTÁCTENOS</b-nav-item>
            </b-navbar-nav>
          </b-collapse>
        </b-container>
      </b-navbar>
      <!-- Mobile Menu End -->
    </section>
    <!--Main Menu/ Mobile Menu Section-->
  </div>
</template>

<script>
import { gql } from 'graphql-request';
export default {
  name: "Header1",
  data(){
      return {
        links: {}
      }
  },
  created() {
    this.fetchData();
  },
  watch: {
    $route: "fetchData",
  },
  methods: {
    async fetchData() {
      this.service = null;
      try {
        const data = await this.$graphcms.request(
          gql`
            query getServicios {
                services {
                    id
                    englishProgram
                    titleLink
                }
            }
          `
        );
        this.links=data.services;
        console.log('links', this.links);
      } catch (e) {
        // handle error
      }
    },
  },

  mounted: function () {
    // Menu Js
    this.$nextTick(function () {
      window.onscroll = function () {
        myFunction();
      };

      var header = document.getElementById("mainNav");
      var sticky = header.offsetTop;

      function myFunction() {
        if (window.pageYOffset > sticky) {
          header.classList.add("navbar-shrink");
        } else {
          header.classList.remove("navbar-shrink");
        }
      }
    });
    // Menu End
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
/* Mobile Dropdown CSS */
.menu-section-area #mainNavMobile.navbar {
  background-color: #54a66a;
  box-shadow: 0 2px 9px rgba(0, 0, 0, 0.2);
  padding: 0 1rem;
}
#mainNavMobile .navbar-toggler {
  color: #fff !important;
}
#mainNavMobile .navbar-nav {
  background: #2c303a;
}
#mainNavMobile .navbar-toggler {
  color: rgba(0, 0, 0, 1);
  border-color: transparent;
  font-size: 34px;
  padding: 0.25rem 0;
}
#mainNavMobile .navbar-nav li.nav-item {
  z-index: 9;
  position: relative;
  border-bottom: 1px solid rgba(0, 0, 0, 0.4);
}
#mainNavMobile .navbar-nav li.nav-item:hover,
#mainNavMobile .navbar-nav li.nav-item.active {
  background-color: #2ca6ef;
}
#mainNavMobile .navbar-nav li:last-child:hover {
  background-color: transparent;
}
#mainNavMobile .navbar-nav .nav-link {
  color: #fff;
  padding: 16px 15px 18px;
  line-height: 15px;
}
.menu-section-area .nav-item.dropdown::before {
  position: absolute;
  right: 15px;
  top: 15px;
  font-size: 20px;
  z-index: -1;
  color: #fff;
}
.menu-section-area .nav-item .nav-link,
ul.dropdown-menu .dropdown-item {
  font-weight: normal;
  font-family: "Lato", sans-serif;
  font-size: 16px;
}
#mainNavMobile .navbar-nav li:last-child span {
  width: auto;
  text-align: center;
  padding: 11px 27px 16px;
}
#mainNavMobile .navbar-nav li .dropdown-item {
  padding: 16px 15px 18px;
}
#mainNavMobile .navbar-nav ul.dropdown-menu li:hover {
  background-color: #2ca6ef;
}
#mainNavMobile .dropdown-item:hover,
#mainNavMobile .dropdown-item:focus {
  color: #fff;
  background-color: transparent;
}
#mainNavMobile .navbar-nav li.nav-item:hover,
#mainNavMobile .navbar-nav li.nav-item.active {
  background-color: #2c303a;
}

.navbar {
  padding: 0.5rem 0rem;
}
.menu-section-area #mainNavMobile.navbar {
  padding: 0;
}

.dropdown-menu {
  border: none;
  border-radius: 0;
}
</style>