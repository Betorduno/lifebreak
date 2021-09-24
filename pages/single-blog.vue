<template>
  <div class="home home-1" id="list-of-sections">
    <Header1 />
    <Banner title="Blogs"/>
    <BlogSinglePageLayout />
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
import Header1 from '@/components/Header1.vue'
import Banner from '@/components/contacts/Banner.vue'
import BlogSinglePageLayout from '@/components/blogs/BlogSinglePageLayout.vue'
import Footer from '@/components/Footer.vue'

export default {
  name: 'BlogSingle',
  components: {
    Header1,
    Banner,
    BlogSinglePageLayout,
    Footer,
  },

}
</script>
