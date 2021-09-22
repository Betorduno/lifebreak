<template>
  <div class="container ">
    <div class="row cont-desc">
      <div class="col-md-6 col-sm-12 col-xs-12">
        <h1>People Talking<br>About Us</h1>
      </div>
      <div class="col-md-6 col-sm-12 col-xs-12">
        <p>...una forma distinta de ver el trabajo, que intenta que este sea una parte integral del estilo de vida, y no compartimentos diferenciados de trabajo y ocio.
          En LifeBreak podrás trabajar cómodamente además de disfrutar de las instalaciones y las variadas actividades que ofrecemos.
          El propósito de nuestro coliving es crear un ambiente internacional y relaciones que vayan más allá de lo profesional, buscando interacciones de aprendizaje y colaboración entre los profesionales que lo habitan y los voluntarios internacionales que ayudan en el proyecto.</p>
      </div>
    </div>
    <div class="row ">
      <div class="col-md-4 col-sm-6 col-xs-12 my-3 type">
        <img src="https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(117).jpg" class="img-fluid" alt="...">
        <h5 class="title">COWORKING</h5>
      </div>
      <div class="col-md-4 col-sm-6 col-xs-12 my-3 type">
        <img src="https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(117).jpg" class="img-fluid" alt="...">
        <h5 class="title">SERVICIOS</h5>
      </div>
      <div class="col-md-4 col-sm-6 col-xs-12 my-3 type">
        <img src="https://mdbootstrap.com/img/Photos/Horizontal/Nature/12-col/img%20(117).jpg" class="img-fluid" alt="...">
        <h5 class="title">ROOMS</h5>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Testimonial'
}
</script>
<style scoped>
  h1 {
    color: #1e3954;
    font-size: 60px;
    font-weight: 500;
    letter-spacing: -3px;
  }

  .container {
    margin-bottom: 10rem;
  }

  .cont-desc {
    margin: 10rem 0 2rem 0;
  }
  .type {
    position: relative;
    display: flex;
    align-items: center;
    align-content: center;
    justify-content: center;
  }
  .title {
    position: absolute;
    top: 50%;
    text-align: center;
    z-index: 10;
    color: #fff;
    font-size: 24px;
    font-weight: 600;
    display: block;
  }
</style>