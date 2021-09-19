<template>
  <div class="container">
    <div class="row my-5">
      <h4 class="subtitle text-center w-100">ABOUT US</h4>
      <h1 class="text-center w-100 my-2 title" v-html="title"></h1>
      <p class="text-center my-4 desc" v-html="description"></p>
      <div class="hero-button-box box-btn">
        <a href="#" class="theme-btn">Leam more</a>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'About',

  data(){
    return {
      title: 'Community, creativity,<br>comfort & more',
      description: 'We are a community of bold minds who have decided to work under the same roof. Our workspace and the people around us inspire us to take action, to grow, to do better. By saying that our coworking space is sustainable and comfy we confirm that you will get 100% satisfaction from working here and making the best out of this experience.'
    }
  }

}
</script>
<style scoped>
 .container {
   padding: 4em 0;
 }
  .box-btn {
    width: 100%;
    text-align: center;
    margin-top: 2em;
  }
  .title {
    color: #1e3954;
    font-size: 60px;
    font-weight: 500;
    letter-spacing: -3px;
  }
  .desc {
    color: #888f96;
    font-size: 20px;
    line-height: 1.8em;
    font-weight: 400;
    padding: 0 10em;
  }
  .subtitle {
    font-weight: 400;
    color:#888f96;
    font-size: 18px;
    margin-bottom: 1.5em;
    letter-spacing: 1.8px;
  }
</style>
