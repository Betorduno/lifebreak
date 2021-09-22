<template>
  <Opinions :images="imgs"/>
</template>

<script>
import Opinions from '@/components/home1/Opinions.vue'
  export default {
    name: 'Slidertestimonial',
    components: {
      Opinions
    },
    data() {
      return {
        imgs: [
          {message: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Assumenda nisi magni reiciendis eveniet commodi, ducimus ullam id suscipit ea fuga rerum sed ab in quos, aspernatur minus est! Perspiciatis, dolore.', autor: 'Jhon Doe', what: 'fundador de apple', src: 'https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(117).jpg'},
          {message: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Assumenda nisi magni reiciendis eveniet commodi, ducimus ullam id suscipit ea fuga rerum sed ab in quos, aspernatur minus est! Perspiciatis, dolore.', autor: 'Jhon Doe', what: 'fundador de apple', src: 'https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(98).jpg'},
          {message: 'lorem ipsum3', autor: 'Jhon Doe', what: 'fundador de apple', src: 'https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(131).jpg'},
          {message: 'lorem ipsum4', autor: 'Jhon Doe', what: 'fundador de apple', src: 'https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(123).jpg'},
          {message: 'lorem ipsum5', autor: 'Jhon Doe', what: 'fundador de apple', src: 'https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(118).jpg'},
          {message: 'lorem ipsum6', autor: 'Jhon Doe', what: 'fundador de apple', src: 'https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(128).jpg'},
          {message: 'lorem ipsum7', autor: 'Jhon Doe', what: 'fundador de apple', src: 'https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(132).jpg'},
          {message: 'lorem ipsum8', autor: 'Jhon Doe', what: 'fundador de apple', src: 'https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(115).jpg'}
        ],
      };
    }
  }
</script>