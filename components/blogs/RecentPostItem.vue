<template>
<client-only>
  <!-- Sidebar Single Widget Start -->
  <div v-if="recient" class="widget widget-recent-posts" id="recent-posts">
    <WidgetTitle title="Recent Posts" />
    <ul>
      <RecentPost v-for="recentPost in recient" :key="recentPost.id" :image="recentPost.image" :altText="recentPost.altText" :title="recentPost.title" :publishDate="recentPost.publishDate" :id="recentPost.url" />
    </ul>
  </div>
</client-only>
  <!-- Sidebar Single Widget End -->
</template>

<script>
import WidgetTitle from '@/components/blogs/WidgetTitle'
import RecentPost from '@/components/blogs/RecentPost'
import { gql } from 'graphql-request';
import moment from 'moment';

export default {
  name: 'RecentPostItem',
  components: {
    WidgetTitle,
    RecentPost

  },
  data(){
    return {
      recentPosts: [
        {id: 1,
        image: require('../../assets/img/blog-page-img/recent-post-1.jpg'),
        altText: 'Recent Post',
        title: 'Business tactics of an agency',
        publishDate: 'July 04, 2019'
        },
        {id: 2,
        image: require('../../assets/img/blog-page-img/recent-post-2.jpg'),
        altText: 'Recent Post',
        title: 'Business tactics of an agency',
        publishDate: 'July 04, 2019'
        },
        {id: 3,
        image: require('../../assets/img/blog-page-img/recent-post-3.jpg'),
        altText: 'Recent Post',
        title: 'Business tactics of an agency',
        publishDate: 'July 04, 2019'
        },
      ],
      recient: []
    }
  },
  methods: {
    async getData() {
      await this.$graphcms.request(
        gql`
          {
            blogs {
              publishDate
              updatedAt
              titlemain
              imagemain {
                id
                url
              }
              id
            }
          }
        `
      ).then((res)=>{
        let resp = res.blogs;
        resp.forEach((recient, idx) => {
          let year = moment(res.blogs[idx].updatedAt).year();
          let yearNow = moment(Date.now()).year();
          if ((yearNow-year) == 0) {
            if (idx <= 4) {
              this.recient.push(
                {
                  image: recient.imagemain.url,
                  altText: 'Recent Post',
                  title: recient.titlemain,
                  publishDate: recient.publishDate,
                  updatedAt:recient.publishDate,
                  day: moment(recient.updatedAt).day(),
                  month: moment(recient.updatedAt).month(),
                  url:`/blogsingle/${recient.id}`
                }
              )
              if (idx>=1) {
                this.recient = this.recient.sort((a, b)=> {
                  if (a.month == b.month ) {
                    if (a.day<b.day ) {
                      return 1
                    }
                    if (a.day>b.day) {
                      return -1
                    }
                    return 0
                  } else {
                    if (a.month<b.month ) {
                      return 1
                    }
                    if (a.month>b.month) {
                      return -1
                    }
                    return 0
                  }
                });
              }
            }

          }
        });
      });
    },
  },
  mounted() {
    this.getData();

  }

}
</script>