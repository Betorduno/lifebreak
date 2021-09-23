<template>
  <div>
    <div class="container">
      <div class="row m-0">
        <div class="col-12 col-lg-5 pb-5">
          <p class="sub-title">REQUEST FOR CALL BACK</p>
          <h1 class="main-title d-flex justify-content-center">
            We're always ready to discuss coperation
          </h1>
        </div>
        <div class="col-12 col-lg-7 m-0">
          <h2 class="Sub-titler">I would like to discuss:</h2>
          <span class="inputtext">
            <div class="efect">
              <input
                class="inputr"
                type="text"
                name="your-name"
                value
                size="62%"
                aria-required="true"
                aria-invalid="false"
                placeholder="Your name"
              />
            </div>
          </span>

          <span class="inputtext">
            <div class="efect">
              <input
                class="inputr"
                type="text"
                name="E-mail"
                value
                size="62%"
                aria-required="true"
                aria-invalid="false"
                placeholder="E-mail"
              />
            </div>
          </span>

          <span class="inputtext">
            <div class="efect">
              <input
                class="inputr"
                type="text"
                name="Message"
                value
                size="62%"
                aria-required="true"
                aria-invalid="false"
                placeholder="Message"
              />
            </div>
          </span>
        </div>
      </div>

       <div class="row m-0">

          <div class="col-12 col-lg-6 justify-content-xs-center mt-5 mb-5">
            <button class="theme-btn">Submit Now</button>
          </div>
          <div class="col-12 col-lg-6 justify-content-lg-center">
            <div class="row m-0">
               <div class="col col-md-10 mt-5 mb-5 ">
              <p class="text-right">Or call us and get free</p>
              <h4 class="text-right">+ 844 123 456 78</h4>
            </div>

            <div class="col col-lg-2 mt-5 mb-5 ">
              <img
                width="55"
                height="55"
                src="https://demo2wpopal.b-cdn.net/co-workshop/wp-content/uploads/2018/11/h4_icon_phone.png"
                data-src="https://demo2wpopal.b-cdn.net/co-workshop/wp-content/uploads/2018/11/h4_icon_phone.png"
                class="
                  elementor-animation-buzz-out
                  attachment-full
                  size-full
                  lazyloaded
                "
                alt=""
              />
            </div>
            </div>
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

.efect:focus-within {
  width: 100%;
  border-bottom: 2px solid #55bbaf;
}
.call {
  font-size: 24px;
  letter-spacing: -1.2px;
  color: #55bbaf;
}
</style>
