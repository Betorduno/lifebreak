<template>
  <div class="container">
    <div class="row">
      <div :key="idx" v-for="(service, idx) in services" class="col-xs-6 col-sm-4 col-md-3 col-lg-3 py-5 px-2 cont-efect d-flex justify-content-center align-items-center  align-content-center justify-content-center flex-column">
        <div class="image-framed ">
          <figure class="image-box-img">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 59 59">
              <path d="M10.407 1.707A.999.999 0 1 0 8.993.293c-11.307 11.307-11.307 29.705 0 41.012a1 1 0 0 0 1.414-1.414C-.12 29.363-.12 12.234 10.407 1.707zM50.005.293a.999.999 0 1 0-1.414 1.414c5.092 5.091 7.896 11.871 7.896 19.092S53.683 34.8 48.591 39.891a.999.999 0 1 0 1.414 1.414c5.47-5.469 8.481-12.751 8.481-20.506S55.475 5.762 50.005.293z"></path><path d="M14.651 5.949a.999.999 0 1 0-1.414-1.414c-8.968 8.968-8.968 23.56 0 32.527a.997.997 0 0 0 1.414 0 .999.999 0 0 0 0-1.414c-8.188-8.188-8.188-21.51 0-29.699zM45.763 4.535a.999.999 0 1 0-1.414 1.414c8.188 8.188 8.188 21.511 0 29.699a.999.999 0 1 0 1.414 1.414c8.968-8.967 8.968-23.559 0-32.527z"></path><path d="M18.893 8.778a.999.999 0 0 0-1.414 0c-3.206 3.206-4.972 7.475-4.972 12.021s1.766 8.814 4.972 12.021a.997.997 0 0 0 1.414 0 .999.999 0 0 0 0-1.414c-5.849-5.849-5.849-15.364 0-21.213.39-.391.39-1.024 0-1.415zM41.521 8.778a.999.999 0 1 0-1.414 1.414c5.849 5.849 5.849 15.364 0 21.213a.999.999 0 1 0 1.414 1.414c3.206-3.206 4.972-7.475 4.972-12.021s-1.766-8.814-4.972-12.02zM29.499 14c-3.859 0-7 3.141-7 7 0 3.519 2.614 6.432 6 6.92V58a1 1 0 1 0 2 0V27.92c3.386-.488 6-3.401 6-6.92 0-3.859-3.14-7-7-7zm0 12c-2.757 0-5-2.243-5-5s2.243-5 5-5 5 2.243 5 5-2.243 5-5 5z">
              </path>
            </svg>
          </figure>
        </div>
        <div class="row d-flex flex-column">
          <h5 class="title-g  text-center mt-4 mb-2">{{service.title}}</h5>
          <p class="desc  text-center">{{service.desc}}</p>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
  export default {
    name: 'Services',
    data() {
      return{
        services: [
          {
            title:'WIFI',
            desc: 'Descripcion del servicio.'
          },
          {
            title:'WIFI',
            desc: 'Descripcion del servicio.'
          },
          {
            title:'WIFI',
            desc: 'Descripcion del servicio.'
          },
          {
            title:'WIFI',
            desc: 'Descripcion del servicio.fdfdfdfdfdfdfdfdfdfdfdfdfdfdfdfdfdfdfdfdf'
          },
          {
            title:'WIFI',
            desc: 'Descripcion del servicio.'
          },
          {
            title:'WIFI',
            desc: 'Descripcion del servicio.'
          },
          {
            title:'WIFI',
            desc: 'Descripcion del servicio.'
          },
          {
            title:'WIFI',
            desc: 'Descripcion del servicio.'
          },
        ]
      }
    }
  }
</script>
<style scoped>
  .cont-efect {
    word-wrap: break-word;
    height: 300px;
  }
  .cont-efect:hover {
    background-color: #55bbaf;
  }

  .image-box-img {
    position: relative;
    width: 95px;
    height: 95px;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    background: #eef8f7;
    border-radius: 50%;
    cursor: pointer;
    transition-duration: .5s;
  }

  .image-box-img svg {
    width: 45px;
    height: 45px;
  }
  .desc {
    display: none;
    width: 12em;
  }
  .cont-efect:hover .desc {
    display: block;
  }

  .cont-efect:hover .title-g, .cont-efect:hover .desc {
    color: #fff;
  }

  .cont-efect:hover .image-box-img {
    animation: beat-after 1.5s ease infinite
  }

  .cont-efect:hover .image-box-img svg {
    fill: #fff;
    animation: zoom-in-zoom-out 2s ease-out infinite;
  }
  .cont-efect:hover .image-box-img  {
    background-color: transparent;
    border: 1px solid rgba(34,34,34,.05);
    animation: zoom-in-zoom-out 2s ease-out infinite;
    transform: translateX(-50%) translateY(-50%);
    transition-duration: .5s;
    content: "";
  }

  @keyframes zoom-in-zoom-out {
    0% {
      transform: scale(0.5, 0.5);
    }
    50% {
      transform: scale(1.1, 1.1);
    }
    100% {
      transform: scale(0.8, 0.8);
    }
  }

  .image-box-img:after {
    content: "";
    position: absolute;
    top: 50%;
    left: 50%;
    background-color: transparent;
    border-radius: inherit;
    box-sizing: content-box;
    transform: translateX(-50%) translateY(-50%);
    transition-duration: .5s;
  }

  .cont-efect:hover .image-box:before {
    animation: beat-before 1.5s ease infinite;
  }

  </style>