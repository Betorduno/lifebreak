<template>
  <div class="col-12 col-sm-12 col-md-12 col-lg-3">
    <aside class="sidebar" id="sidebar">
      <!-- Sidebar Single Widget Start -->
      <RecentPostItem />
      <!-- Sidebar Single Widget End -->
    </aside>
  </div>
</template>

<script>
import RecentPostItem from '@/components/blogs/RecentPostItem'

export default {
  name: 'BlogSidebar',
  components: {
    RecentPostItem,
  }

}
</script>