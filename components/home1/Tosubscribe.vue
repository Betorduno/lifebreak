<template>
  <div class="d-flex justify-content-center bg-blue parallax">
    <div class="row m-0 d-flex justify-content-center flex-column my-5">
      <h2 class="text-center title mb-4">Contacta con nosotros</h2>
      <p class="text-center desc mb-4">Subcríbete a nuestro boletin para mas información.</p>
    <b-form  @submit.stop.prevent="postData" id="form-all">
      <div class="p-2 row text-center d-flex justify-content-center flex-row designForm"  id="feedback-user">
        <div class="col-xs-4 col-sm-4 col-md-8">
          <b-form-input class="input-email" autocomplete="off" v-model="email" placeholder="">
        </b-form-input></div>
        <div class="col-xs-4 col-sm-4 col-md-2">
          <b-button  type="submit" class="theme-btn">Enviar</b-button>
        </div>
      </div>

      <b-form-invalid-feedback :state="validation">
        El email ingresado no es valido.
      </b-form-invalid-feedback>
      <p id="all-status"></p>
     </b-form>
  </div>
  </div>
</template>

<script>
  export default {
    name: 'Tosubscribe',
    data() {
      return {
        email: ''
      }
    },
    computed: {
      validation() {
        if (this.email.length > 0) {
          const re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
          return re.test(this.email)
        }
      }
    },
    methods: {
      postData(){
        let status = document.getElementById("all-status");
        let form = document.getElementById("form-all");
        if (this.email != '' && this.email != null) {
          fetch('https://formspree.io/f/xdoyjnjj', {
            method: 'POST',
            body: JSON.stringify({ email: this.email, message: 'Quiero que me envien información!'}),
            headers: {
                'Accept': 'application/json'
            }
          }).then(response => {
            form.reset();
            status.innerHTML = "Gracias por tu suscripción!";

          }).catch(error => {
            status.innerHTML = "Oops! There was a problem submitting your form"
          });
        }
        }

    }
  }
</script>
<style scoped>

  .parallax {
    /* The image used */
    background-image: url("@/assets/img/bannersubcribe.jpg") !important;

    /* Set a specific height */
    min-height: 500px;
    padding: 150px 30px 190px;
    width: 100%;

    /* Create the parallax scrolling effect */
    background-attachment: fixed;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
  }
  .title {
    font-size: 64px;
    line-height: 64px;
    color: white;
  }

  .desc {
    color: rgba(255,255,255,.83);
    font-size: 20px;
    font-weight: 400;
    line-height: 30px;
  }

  input:-internal-autofill-selected {
    background-color: #fff !important;
  }

  .theme-btn {
    padding: 0;
    border: 0;
    width: 100px;
    line-height: 50px;
  }
  .theme-btn:hover {
    background-color: #3f9d92;
    border-color: #3f9d92;
    color: white;
  }
  .theme-btn:hover {

  }

  .designForm {
    display: block;
    padding: 10px;
    background-color: #fff;
    border-radius: 32px 32px 32px 32px;
  }

  .designForm .input-email {
    background-color: transparent;
    width: 100%;
  }
</style>