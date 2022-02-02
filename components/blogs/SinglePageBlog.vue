<template>
<client-only>
  <div v-if="dataAll" id="content">
    <!-- Block 1-->
    <div class="block-1">
      <div class="card">
        <img :src="image" :alt="altText">
        <div class="card-body">
          <h2 class="card-title">{{title}}</h2>
          <div class="card-footer d-flex">
            <div class="card-footer-box d-flex">
              <div class="author-box"><span>By {{publishBy}}</span></div>
              <div class="blog-date"><i class="far fa-calendar-alt"></i> {{publishDate}}</div>
              <div class="card-footer-share">
                <i class="far fa-comments"></i> {{commentNumber}}
              </div>
            </div>
          </div>
        </div>
      </div>

      <p>{{content1}}</p>

      <blockquote class="position-relative">
        <p>{{quoteText}}</p>
      </blockquote>

      <p>{{content2}}</p>

        <div class="blog-content-with-media">
          <div class="blog-media-content">
            <h6 class="blog-content-with-media-title">{{mediaTitle}}</h6>
            <p>{{content3}}</p>
            <p>{{content4}}</p>
          </div>

          <div class="blog-media-box d-inline-flex justify-content-center align-items-center position-relative">
            <img :src="mediaImage" :alt="mediaAltText">
          </div>

        </div>

    </div>
    <!-- Block 1-->
</div>
</client-only>
</template>

<script>
import PopularTag from '@/components/blogs/PopularTag'
import AuthorSocialLinkItem from '@/components/blogs/AuthorSocialLinkItem'
import { gql } from 'graphql-request';

export default {
  name: 'SinglePageBlog',

  components: {
    PopularTag,
    AuthorSocialLinkItem
  },

  data() {
    return {
      dataAll:{},
      image: '',
      altText: '',
      title: '',
      publishBy: '',
      publishDate: '',
      commentNumber: '',
      content1: '',
      quoteText: '',
      content2: '',
      content3: '',
      content4: '',
      mediaImage: '',
      mediaAltText: '',
      mediaTitle: ''
    }
  },
  created() {
    this.fetchData();
  },
  watch: {
    $route: 'fetchData',
  },
  methods: {
    async fetchData() {
      this.service = null
      try {
        const data = await this.$graphcms.request(
          gql`
            query getBlog($id: ID!) {
              blog(where: { id: $id }) {
                titlemain
                contentblog {
                  ... on BllogPaginaSimple {
                    id
                    image {
                      url
                    }
                    mediaImage {
                      url
                    }
                    title
                    altText
                    publishBy
                    showContent1
                    showContent2
                    showContent3
                    showQuote
                    showcontent4
                    content1
                    content2
                    content3
                    content4
                    quoteText {
                      text
                    }
                  }
                }
                publishDate
              }
            }
          `,
          {
            id: this.$route.params.singleblog,
          }
        );
        this.dataAll = data;
        this.image= data.blog.contentblog.image.url,
        this.altText= data.blog.contentblog.altText,
        this.title= data.blog.contentblog.title,
        this.publishBy= data.blog.contentblog.publishBy,
        this.publishDate= data.blog.publishDate,
        this.commentNumber= '',
        this.content1= data.blog.contentblog.content1,
        this.quoteText= data.blog.contentblog.quoteText.text,
        this.content2= data.blog.contentblog.content2,
        this.content3= data.blog.contentblog.content3,
        this.content4= data.blog.contentblog.content4,
        this.mediaImage= data.blog.contentblog.mediaImage.url,
        this.mediaAltText= data.blog.contentblog.altText,
        this.mediaTitle= data.blog.
        console.log('esta es la data de blog= ', data.blog);
      } catch (e) {
        // handle error
        console.log('hola')
        // window.location.href="/"
      }
    },
  },
  mounted() {
    console.log('>>>>>>>>>>>>>>>>>>>>',this.$route.params.singleblog)
  }
}
</script>