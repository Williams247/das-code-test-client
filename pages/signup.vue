<template>
  <div class="mt-3">
    <div class="card square-card pt-5 pb-5">
      <div class="card-body px-5 py-4">
        <div class="row">
          <div class="col-lg-6">
            <auth-button auth-button-type="facebook" auth-button-text="Sign up with Facebook" />
          </div>
          <div class="col-lg-6">
            <auth-button auth-button-type="google" auth-button-text="Sign up with Google" />
          </div>
        </div>
        <div class="px-4">
          <div class="hr"></div>
          <div class="d-flex justify-content-center">
              <div class="hr-text">or log in with</div>
          </div>
          <form @submit.prevent="handleLogin">
          <div class="mt-4">
              <div class="form-input-outline mt-4 pt-3" ref="email_field">
                  <div class="d-flex py-2 form-space">
                      <Mail />
                      <input type="email" class="auth-input col-lg-11" placeholder="Email Address" @click="handleFocused('email-field')" @blur="handleUnFocused" />
                  </div>
              </div>
              <div class="form-input-outline mt-4 pt-3" ref="password_field">
                   <div class="d-flex py-2 form-space">
                      <Lock />
                      <input
                        :id="[isPasswordView ? 'hide':'show']"
                        :type="[isPasswordView ? 'text':'password']"
                        class="auth-input col-lg-11"
                        placeholder="Password"
                        @click="handleFocused('password-field')"
                        @blur="handleUnFocused"
                     />
                      <div class="cursor-pointer" @click="handleChangePasswordView">
                          <font-awesome-icon :icon="['fas', `${isPasswordView ? 'eye':'eye-slash'}`]" />
                      </div>
                  </div>
              </div>
          </div>
          <div class="mt-5">
              <action-button
                action-button-type="submit"
                variant="primary"
                :loading="loading"
                :label="loading ? 'Loading...':'Sign Up'"
                measurement="py-3 mt-5"
              />
          </div>
          <div class="text-center auth-option mt-4 alternative">
              Already have an account?
              <nuxt-link to="/login">
                <span class="font-weight-bold">Log In</span>
              </nuxt-link>
          </div>
          </form>
          <!--end of line-->
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Login',
  layout: 'unauthenticated',
  data () {
    return {
      isPasswordView: false,
      loading: false
    }
  },
  methods: {
    handleChangePasswordView () {
      this.isPasswordView = !this.isPasswordView
    },
    handleLogin () {
      alert()
    },
    handleUnFocused () {
      const emailField = this.$refs.email_field
      const passwordField = this.$refs.password_field
      emailField.classList.remove('focused')
      passwordField.classList.remove('focused')
    },
    handleFocused (field) {
      const emailField = this.$refs.email_field
      const passwordField = this.$refs.password_field

      if (field === 'email-field') {
        passwordField.classList.remove('focused')
        emailField.classList.add('focused')
      } else if (field === 'password-field') {
        emailField.classList.remove('focused')
        passwordField.classList.add('focused')
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.hr {
  width: 100%;
  margin-top: 50px;
  height: 1px;
  background: #DEDEDE;
}

.hr-text {
  background: white;
  height: 30px;
  margin-top: -16px;
  text-align: center;
  @media (min-width: 800px) {
    width: 20%;
  }
}

.form-space {
  @media (min-width: 800px) {
    padding-left: 20px;
    padding-right: 20px;
    input[type=email],
    input[type=password] {
      padding-left: 20px;
      padding-right: 20px;
    }
  }
}

.forgot-password-text {
  font-size: 18px;
  color: #000000;
  opacity: 0.3;
}

.auth-option {
  color: black;
}

.focused {
  border-bottom: 1px solid #757575;
}

#hide {
  padding-right: 0;
  @media (min-width: 800px) {
    padding-left: 20px;
  }
}
</style>
