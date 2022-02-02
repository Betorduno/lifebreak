<template>
<client-only>
  <div v-if="blogs" id="content">
    <BlogClassicItem v-for="blog in itemsForList" :key="blog.id"
        :image="blog.imagemain.url"
        :altText="blog.altText"
        :title="blog.titlemain"
        :publishBy="blog.publishBy"
        :publishDate="blog.publishDate"
        :commentNumber="blog.commentNumber"
        :description="blog.descriptionmain"
        :btnText="blog.btnText"
        shareText="Compartir"
        :id="blog.id"
      />

    <!-- Blog Pagination Box-->
    <nav class="pagination-area">

      <b-pagination
        v-model="currentPage"
        pills
        :total-rows="rows"
        :per-page="perPage"
        first-text="Primero"
        prev-text="Anterior"
        next-text="Siguiente"
        last-text="Ultimo">
      </b-pagination>

    </nav>

    <!-- Blog Pagination Box-->
</div>
</client-only>
</template>

<script>
import BlogClassicItem from '@/components/blogs/BlogClassicItem'
import { gql } from 'graphql-request';

export default {
  name: 'ClassicPageBlog',
  components: {
    BlogClassicItem
  },
  data() {
    return {
      blogs: new Array(),
      rows: '',
      perPage: 1,
      currentPage: 1
    }
  },
  computed: {
    itemsForList() {
      return this.blogs.slice(
        (this.currentPage - 1) * this.perPage,
        this.currentPage * this.perPage,
      );
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
            query getBlogs {
                 blogs {
                  id
                  imagemain {
                    url
                  }
                  altText
                  titlemain
                  descriptionmain
                  publishBy
                  publishDate
                  btnText
                }
            }
          `
        );

        data.blogs.forEach(element => {
          this.blogs.push(element)
        });

        this.rows = this.blogs.length;
        console.log('este es rows: ',this.rows);
      } catch (e) {
        // handle error
      }
    }
  }
}
</script>