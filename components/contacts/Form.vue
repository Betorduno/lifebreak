<template>
  <div>
    <div class="container pt-5">
      <div class="row m-0">
        <div class="col-12 col-lg-5 pb-5">
          <p class="sub-title">REQUEST FOR CALL BACK</p>
          <h1 class="main-title d-flex justify-content-center">
            We're always ready to discuss coperation
          </h1>
        </div>
        <div class="col-12 col-lg-7 m-0 ">
          <h2 class="Sub-titler text-left">I would like to discuss:</h2>
         <div class="row ">
           <div class="col-12">
              <span class="inputtext ">
            <div class="efect">
              <input
                class="inputr"
                type="text"
                name="your-name"
                value
                size="40%"
                aria-required="true"
                aria-invalid="false"
                placeholder="Your name"
              />
            </div>
          </span>
           </div>
         </div>
        
         <div class="row ">
            <div class="col-12">
              <span class="inputtext">
            <div class="efect">
              <input
                class="inputr"
                type="text"
                name="E-mail"
                value
                size="40%"
                aria-required="true"
                aria-invalid="false"
                placeholder="E-mail"
              />
            </div>
          </span>
            </div>
         </div>
          <div class="row ">
           <div class="col-12">
              <span class="inputtext  ">
            <div class="efect ">
              <input
                class="inputrm "
                type="text"
                name="Message"
                value
                size="40%"
                aria-required="true"
                aria-invalid="false"
                placeholder="Message"
              />
            </div>
          </span>
           </div>
          </div>
          
        </div>
        <div
          class=" hero-button-box box-btn col-12 offset-md-5 mt-5 text-md-left text-sm-center text-center pb-5"
        >
          <button class="theme-button ">Submit Now</button>
        </div>
      </div>
    </div>
    <div class="container-fluid px-0">
      <div class="row m-0 ">
        <div class="col-12 px-0">
          <iframe
            src="https://www.google.com/maps/embed?pb=!1m10!1m8!1m3!1d24192.12784494103!2d-73.9575933!3d40.7176647!3m2!1i1024!2i768!4f13.1!5e0!3m2!1svi!2s!4v1542103385590"
            height="280"
            frameborder="0"
            style="border:0"
            allowfullscreen
          >
          </iframe>
        </div>
      </div>
    </div>
  </div>
</template>
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

.efect:focus-within {
  width: 100%;
  border-bottom: 2px solid #55bbaf;
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
