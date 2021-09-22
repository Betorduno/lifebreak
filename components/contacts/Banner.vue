<template>
  <div>
    <!-- Header Start -->
    <header class="page-banner-area" id="home">
      <div class="section-overlay d-flex">
        <div class="container">
          <div class="header-caption position-relative wow fadeInLeft d-flex">
            <h1 class="header-caption-heading text-capitalize">Contact Us</h1>
            <nav aria-label="breadcrumb">
              <b-breadcrumb :items="items"></b-breadcrumb>
            </nav>
          </div>
        </div>
      </div>
    </header>
    <!-- Header End -->
  </div>
</template>
<style>

</style>
<script>
export default {
  name: "Banner",
  data() {
    return {
      items: [
        {
          text: "Home",
          to: "/"
        },
        {
          text: "Contact Us",
          active: true
        }
      ]
    };
  }
};
</script>
