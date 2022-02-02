<template>
  <div>
    <client-only>
    <div class="container pt-5">
      <div class="row m-0">
        <div class="col-12 col-lg-5 pb-5">
          <p class="sub-title">LIFEBREAK BY IMUKO</p>
          <h1 class="main-title d-flex justify-content-center">
            Se parte de nuestra experiencia
          </h1>
        </div>
        <div class="col-12 col-lg-7 m-0 ">
          <h2 class="Sub-titler text-left">Déjanos tu contacto:</h2>
           <b-form  @submit.stop.prevent="onSubmit" id="form-all">
            <div class="inputtext ">
                <input v-model="name" class="inputr" type="text" placeholder="Nombre"
                />
                <div class="efect">
              </div>
            </div>

            <div class="inputtext ">
                <input v-model="email" type="email" class="inputr" placeholder="E-mail"
                />
                <div class="efect">
                </div>
            </div>

            <div class="inputtext ">

                <input v-model="message" class="inputr" type="text" placeholder="Mensaje"
                />
              <div class="efect">
              </div>
            </div>
            <div class="my-5">
              <button t ype="submit" class="theme-button ">Enviar</button>
            </div>
          </b-form>
          <b-alert
              id="all-status"
              :show="dismissCountDown"
              dismissible
              :variant="typealert"
              @dismissed="dismissCountDown=0"
              @dismiss-count-down="countDownChanged"
            >
              {{msg}}
          </b-alert>


        </div>
      </div>
    </div>
    <div class="container-fluid px-0">
      <div class="row m-0 ">
        <div class="col-12 px-0">
          <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3966.597202464541!2d-75.2233040848039!3d6.184626728724663!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8e46a7999d1506eb%3A0xde7e5adc664f658b!2sLifebreak!5e0!3m2!1ses-419!2sco!4v1632513848490!5m2!1ses-419!2sco"
          height="280"
          style="border:0;"
          frameborder="0"
          allowfullscreen
          loading="lazy">
          </iframe>
        </div>
      </div>
    </div>
    </client-only>
  </div>
</template>
<script>
  export default {
    name: 'Tosubscribe',
    data() {
      return {
        name: '',
        email: '',
        message: '',
        msg:'',
        dismissSecs: 5,
        dismissCountDown: 0,
        typealert:'info'
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
      onSubmit(){
        let status = document.getElementById("all-status");
        let form = document.getElementById("form-all");
          if (this.email != '' && this.email != null && this.name != '' && this.message != '') {
            fetch('https://formspree.io/f/mvodypea', {
              method: 'POST',
              body: JSON.stringify({
                name: this.name,
                email: this.email,
                message: this.message}),
              headers: {
                  'Accept': 'application/json'
              }
            }).then(response => {
              form.reset();
              this.typealert ='success'
              this.msg ="Gracias por tu suscripción!"
              this.showAlert();
            }).catch(error => {
              this.typealert ='danger'
              this.msg='Oops! There was a problem submitting your form'
              this.showAlert();
            });
          }
          else {
            this.msg = "Llene todos los campos del formulario!";
            this.typealert ='danger';
            this.showAlert();
          }
        },

        countDownChanged(dismissCountDown) {
          this.dismissCountDown = dismissCountDown;
        },
        showAlert() {
          this.dismissCountDown = this.dismissSecs;
        }

    }
  }
</script>
<style scoped>
.sub-title {
  font-size: 16px;
  font-weight: 550;
  text-transform: uppercase;
  letter-spacing: 0.8px;
  color: rgba(136, 143, 150, 0.6);
}
.main-title {
  font-size: 50px;
  font-weight: 600;
  letter-spacing: -1.4px;
  font-family: "Mukta", -apple-system, BlinkMacSystemFont, Sans-serif;
}
.Sub-titler {
  font-size: 18px;
  font-weight: 550;
  font-family: "Mukta", -apple-system, BlinkMacSystemFont, Sans-serif;
  color: #1e3954;
}

.efect {
  width: 0px;
  border-bottom: 2px solid #55bbaf;
  transition: width 1s;
}

.inputtext:hover .efect {
  width: 100%;
}

.inputr {
  font-size: 16px;
  font-weight: 400;
  color: rgba(136, 143, 150, 0.6);
  background-color: transparent;
  border-style: solid;
  border-width: 0 0 2px;
  border-color: rgba(188, 188, 188, 0.2);
  padding: 10px 0;
  height: 70px;
  width: 100%;
}
.inputrm {
  font-size: 16px;
  font-weight: 400;
  color: rgba(136, 143, 150, 0.6);
  background-color: transparent;
  border-style: solid;
  border-width: 0 0 2px;
  border-color: rgba(188, 188, 188, 0.2);
  padding: 10px 0;
  height: 140px;
}

.inputtext:focus-within .inputr {
  width: 100%;
  border-bottom: 2px solid #55bbaf;
}
.inputtext:focus-within .efect {
  width: 0%;
  border-bottom: 0;
}
.call {
  font-size: 24px;
  letter-spacing: -1.2px;
  color: #55bbaf;
}
iframe {
  max-width: 100%;
  width: 100%;
  margin: 0;
  line-height: 1;
}


</style>
