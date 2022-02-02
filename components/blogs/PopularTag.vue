<template>
<client-only>
  <li>
    <a href="#">{{tagTitle}}</a>
  </li>
</client-only>
</template>

<script>
export default {
  name: 'PopularTag',
  props: {
    tagTitle: String
  }
}
</script>