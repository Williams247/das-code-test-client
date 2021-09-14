<template>
  <div>
    <div id="first-container" class="d-flex justify-content-center py-5">
      <div class="payment-container mt-5 space-bottom">
        <div id="buy-course" class="text-center">
          Buy Course
        </div>
        <div id="name-of-course" class="mt-4 text-center">Name of Course</div>
        <div id="course-fee" class="mt-4 text-center">₦10,000</div>
        <div id="start-date" class="mt-4 text-center">Next Cohort begins: 5th of September, 2021 | Duration: 2 weeks</div>
      </div>
    </div>
    <div id="second-container" class="d-flex justify-content-center py-5">
        <div class="payment-container px-2">
            <div class="card remove-card-border card-dark-shadow py-3 card-top-space accordion-card">
               <div class="px-5">
                <div class="proceedure px-4">
                  Existing user? <nuxt-link class="login-link" to="">Log In</nuxt-link>
                </div>
                <form>
                <div class="mt-2">
                  <div class="form-desc mt-5 px-4">Personal Information</div>
                  <div class="d-flex flex-direction-row-column">
                    <div class="col-lg-6 px-3">
                      <div class="form-input-outline mt-4 pt-3" ref="email_field">
                        <div class="d-flex py-2 px-4">
                            <input type="text" class="auth-input col-lg-11" placeholder="First Name" />
                        </div>
                      </div>
                    </div>
                    <div class="col-lg-6 px-3">
                      <div class="form-input-outline mt-4 pt-3" ref="email_field">
                        <div class="d-flex py-2 px-4">
                            <input type="text" class="auth-input col-lg-11" placeholder="Last Name" />
                        </div>
                      </div>
                    </div>
                  </div>
                  <div class="d-flex flex-direction-row-column">
                    <div class="col-lg-6 px-3">
                      <div class="form-input-outline mt-4 pt-3" ref="email_field">
                        <div class="d-flex py-2 px-4">
                            <input type="email" class="auth-input col-lg-11" placeholder="Email Address" />
                        </div>
                      </div>
                    </div>
                    <div class="col-lg-6 px-3">
                      <div class="form-input-outline mt-4 pt-3" ref="email_field">
                        <div class="d-flex py-2 px-4">
                            <input type="number" class="auth-input col-lg-11" placeholder="Phone Number" />
                        </div>
                      </div>
                    </div>
                  </div>
                  <!---end of line--->
                </div>
                <div class="mt-2">
                  <div class="form-desc mt-5 px-4">Personal Information</div>
                  <div class="px-3 mt-4">
                    <select id="payment-dropdown" class="col-lg-12 px-5 py-3">
                      <option>Please choose a payment method</option>
                      <option>Optiion one</option>
                      <option>Optiion one</option>
                    </select>
                  </div>
                  <div>
                  <div class="form-desc mt-5 px-4">Enter card details</div>
                  <div class="d-flex flex-direction-row-column">
                    <div class="col-lg-6 px-3">
                      <div class="form-input-outline mt-4 pt-3" ref="email_field">
                        <div class="d-flex py-2 px-4">
                            <input type="number" class="auth-input col-lg-11" placeholder="Card Number" />
                        </div>
                      </div>
                    </div>
                    <div class="col-lg-6 px-3">
                      <div class="form-input-outline mt-4 pt-3" ref="email_field">
                        <div class="d-flex py-2 px-4">
                            <input type="text" class="auth-input col-lg-11" placeholder="Exp" />
                        </div>
                      </div>
                    </div>
                  </div>
                  </div>
                  <div class="d-flex flex-direction-row-column">
                    <div class="col-lg-6 px-3">
                      <div class="form-input-outline mt-4 pt-3" ref="email_field">
                        <div class="d-flex py-2 px-4">
                            <input type="number" class="auth-input col-lg-11" placeholder="CVV" />
                        </div>
                      </div>
                    </div>
                  </div>
                  <!---end of line--->
                </div>
                <div class="d-flex justify-content-center mt-3 pb-5">
                <div class="col-lg-3 pb-5">
                  <action-button
                      action-button-type="submit"
                      variant="primary"
                      :loading="loading"
                      :label="loading ? 'Loading...':`Pay ₦${'10,000'}`"
                      measurement="py-2 mt-5 round"
                    />
                  </div>
                 </div>
                </form>
               </div>
            </div>
        </div>
    </div>
  </div>
</template>

<script>
import faqData from '../constants/faqs-button.json'
import accordionData from '../constants/accordion.json'
export default {
  name: 'Faqs',
  data () {
    return {
      faqData,
      accordionData,
      loading: false
    }
  }
}
</script>

<style lang="scss" scoped>
@import "~/assets/css/index.scss";
.payment-container {
    width: 86.5%;
}
.login-link {
  color: $primary !important;
  font-weight: bold;
}
#first-container {
  background: $layout-background;
   .space-bottom {
    padding-bottom: 200px;
  }
  #buy-course {
    font-style: normal;
    font-weight: normal;
    font-size: 18px;
    line-height: 28px;
    color: #000000;
  }
  #name-of-course {
    font-family: Inria Serif;
    font-style: normal;
    font-weight: bold;
    font-size: 36px;
    line-height: 43px;
    color: $primary;
  }
  #course-fee {
    font-style: normal;
    font-weight: 600;
    font-size: 28px;
    line-height: 34px;
    text-transform: uppercase;
    color: $primary;
  }
  #faq-button-container {
    padding-bottom: 100px;
  }
}

#second-container {
   background: $layout-background-2;
   .proceedure {
      font-style: normal;
      font-weight: normal;
      font-size: 12px;
      line-height: 25px;
      color: #000000;
   }
}

.card-top-space {
  padding-top: 40px !important;
  padding-bottom: 60px !important;
}

.accordion-card {
  @media (min-width: 800px) {
    margin-top: -240px;
  }
}

.form-desc {
  font-style: normal;
  font-weight: bold;
  font-size: 14px;
  line-height: 155.02%;
  color: $primary;
}

#payment-dropdown {
  border: 0.5px solid rgba(2, 3, 4, 0.4);
  box-sizing: border-box;
  border-radius: 4px;
  &:focus {
    outline: none !important;
  }
}

#third-container {
   background: $layout-background-2;
   #question-head {
      font-style: normal;
      font-weight: normal;
      font-size: 21px;
      line-height: 155.02%;
      text-align: center;
      color: #000000;
   }
   #question-text {
      font-style: normal;
      font-weight: normal;
      font-size: 13px;
      text-align: center;
      color: #000000;
      padding-bottom: 130px;
   }
}

.focused {
  border-bottom: 1px solid #757575;
}
</style>
