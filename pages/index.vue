<template>
  <div>
    <div class="d-flex justify-content-center">
      <div class="col-lg-9">
        <div id="top-text" class="mt-4 pt-5 text-center">
          Lorem Ipsum Dolor sit amet
        </div>
        <div id="top-text-2" class="text-center pt-2 mt-1">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. <br />
          Volutpat ipsum rhoncus, convallis nisi, eget.
        </div>
        <div class="d-flex justify-content-center pt-4">
          <action-button
            variant="primary"
            action-button-type="button"
            measurement="px-4 py-2"
            label="Get Started"
          />
        </div>
        <div class="d-flex justify-content-center">
            <img class="mt-5" src="/images/langing-page-image.jpg" />
        </div>
        <div class="spacing mt-5">
          <div class="d-flex flex-direction-row-column">
            <div class="col-lg-4">
              <div class="small-text plg-1">Lorem Ipsum</div>
              <div class="big-text">X Courses</div>
            </div>
            <div class="col-lg-4">
               <div class="small-text text-center">Lorem Ipsum</div>
               <div class="big-text text-center">X Courses</div>
            </div>
            <div class="col-lg-4">
              <div class="small-text plg-2">Lorem Ipsum</div>
              <div class="big-text plg-3">X Courses</div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!---end of line--->
    <div id="containment">
      <div class="d-flex justify-content-center">
        <div class="container">
          <div class="d-flex flex-direction-row-column">
            <div class="col-lg-5">
              <img class="circle-image" src="/images/ellipse.png" />
            </div>
            <div id="ptp" class="col-lg-5">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vulputate commodo nisi, vestibulum blandit lectus eget
              non sodales leo. Orci netus morbi hac aliquam, erat eget. Fermentum, scelerisque vel sodales duis sed. Ut justo, velit,
              tincidunt purus tortor at congue vitae sit. Ullamcorper mauris vel tellus, venenatis,
              tristique dictum viverra felis. Ligula eu, interdum nulla ac lorem.
            </div>
          </div>
        </div>
      </div>
    </div>
    <div id="containment-2">
      <div class="d-flex justify-content-center">
        <div id="containment-2-text" class="col-lg-10">
         <div class="d-flex flex-direction-row-column">
           <div class="col-lg-6">
             <div id="containment-2-text">
                Lorem Ipsum Dolor sit
             </div>
             <div id="containment-2-text-subheading">Lorem ipsum dolor sit amet, consectetur adipiscing elit ondimentum.</div>
           </div>
           <div class="col-lg-6">
             <div class="float-right">
               <div id="carousel-button-container" class="d-flex">
                 <div>
                   <carousel-button arrow-position="left" />
                 </div>
                 <div class="right-btn">
                   <carousel-button arrow-position="right" />
                 </div>
               </div>
             </div>
           </div>
         </div>
         test
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LandingPage'
}
</script>

<style lang="scss" scoped>
@import '~/assets/css/index.scss';

#top-text {
  font-family: Inria Serif;
  font-style: normal;
  font-weight: bold;
  font-size: 30px;
  line-height: 43px;
  color: #000000;
}

.spacing {
  padding-left: 100px;
  padding-right: 100px;
}

.small-text {
  font-family: sans-serif;
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 17px;
  color: #000000;
  opacity: 0.5;
}

.big-text {
  font-family: sans-serif;
  font-style: normal;
  font-weight: 800;
  font-size: 28px;
  line-height: 34px;
  color: #000000;
}

.plg-1 {
  @media (min-width: 800px) {
    padding-left: 38px;
  }
}

.plg-2 {
  @media (min-width: 800px) {
    padding-left: 120px;
  }
}

.plg-3 {
  @media (min-width: 800px) {
    padding-left: 80px;
  }
}

#containment {
  background: white;
  margin-top: 80px;
  padding-top: 80px;
  padding-bottom: 80px;
}

.circle-image {
  width: 325px;
  height: 325px;
  @media (min-width: 800px) {
    margin-left: 80px;
  }
}

#ptp {
  font-size: 18px;
  font-style: normal;
  font-weight: normal;
  font-size: 18px;
  line-height: 165.52%;
  text-align: justify;
  @media (min-width: 800px) {
    padding-top: 70px;
  }
}

#containment-2 {
  background: $layout-background-2;
  padding-top: 90px;
  padding-bottom: 90px;
  #containment-2-text {
    font-family: Inria Serif;
    font-style: normal;
    font-weight: bold;
    font-size: 31px;
    line-height: 37px;
    color: #000000;
  }
  #containment-2-text-subheading {
    font-style: normal;
    font-weight: 300;
    font-size: 18px;
    line-height: 150.02%;
    color: #000000;
    margin-top: 8px;
  }
  .right-btn {
    margin-left: 9px;
  }
}

#carousel-button-container {
  width: 100px;
  margin-top: 25px;
}
</style>
