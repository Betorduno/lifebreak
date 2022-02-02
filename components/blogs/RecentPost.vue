<template>
<client-only>
  <li>
    <router-link :to="`${id}`" class="d-flex align-items-center">
      <img class="image" :src="image" :alt="altText">
      <p class="title">{{title}}<span>{{publishDate}}</span></p>
    </router-link>
  </li>
</client-only>
</template>
<style scoped>
.title {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
.image {
  width: 85px;
}
</style>

<script>
export default {
  name: 'RecentPost',
  props: {
    image: String,
    altText: String,
    title: String,
    publishDate: String,
    id: String
  }
}
</script>