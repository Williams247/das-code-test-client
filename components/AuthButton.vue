<template>
  <div>
    <button v-if="authButtonType === 'facebook'" class="btn d-flex auth-button px-4 auth-facebook-button">
      <div>
        <img class="button-image" src="/images/facebook.png" />
      </div>
      <div class="auth-button-text">{{ authButtonText }}</div>
    </button>
    <button v-if="authButtonType === 'google'" class="btn d-flex auth-button px-4 auth-google-button">
      <div>
        <img class="button-image" src="/images/google.png" />
      </div>
      <div class="auth-button-text">{{ authButtonText }}</div>
    </button>
  </div>
</template>

<script>
export default {
  name: 'AuthButton',
  props: {
    authButtonType: {
      type: String,
      default: 'facebook'
    },
    authButtonText: {
      type: String,
      default: ''
    }
  }
}
</script>

<style lang="scss" scoped>
.auth-button {
  border: 1px solid #cccccc;
  box-sizing: border-box;
  border-radius: 20px;
  width: 90%;
  transition: 555ms ease;
  .auth-button-text {
    margin-top: 5px;
    margin-left: 6px
  }
  &:hover {
    transform: scale(.9);
  }
}
.auth-facebook-button {
 @media (min-width: 800px) {
   margin-left: 15px;
 }
}

.auth-google-button {
 @media (min-width: 800px) {
   margin-left: 15px;
 }
}

.button-image {
  width: 36px;
}
</style>
