<template>
  <div>
    <!-- Header Start -->
    <header class="page-banner-area" id="home">
      <div class="section-overlay d-flex">
        <div class="container">
          <div class="header-caption position-relative wow fadeInLeft d-flex">
            <h1 class="header-caption-heading text-capitalize">{{title}}</h1>

          </div>
        </div>
      </div>
    </header>
    <!-- Header End -->
  </div>
</template>
<script>
export default {
  name: "Banner",
  props: {
    title: {
        type: String,
        required: true,
    }
  },
  data() {
    return {
      items: [
        {
          text: "Home",
          to: "/"
        },
        {
          text: this.title,
          active: true
        }
      ]
    };
  }
};
</script>
