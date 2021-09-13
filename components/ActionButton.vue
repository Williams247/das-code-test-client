<template>
  <div>
    <button
      v-if="variant === 'primary'"
      :type="actionButtonType"
      :disabled="loading"
      :class="`text-center btn primary-button-background ${measurement}`"
    >
      <span
        v-if="loading"
        class="spinner-border spinner-border-sm"
        role="status"
        aria-hidden="true"
      />
      {{ label }}
    </button>
    <!-- <button v-if="variant === 'primary-outlined'" :type="actionButtonType" :disabled="loading" :class="`text-center primary-outline-button-background ${measurement}`">
           <span v-if="loading" class="spinner-border spinner-border-sm" role="status" aria-hidden="true"></span> {{ label }}
    </button>-->
  </div>
</template>

<script>
export default {
  name: 'ActionButton',
  props: {
    actionButtonType: {
      type: String,
      default: ''
    },
    variant: {
      type: String,
      default: ''
    },
    label: {
      type: String,
      default: ''
    },
    loading: {
      type: Boolean,
      default: false
    },
    measurement: {
      type: String,
      default: ''
    }
  }
}
</script>

<style lang="scss" scoped>
@import '~/assets/css/index.scss';
.primary-button-background {
  background: $primary;
  border-radius: 15px;
  width: 100%;
  color: white;
  &:hover {
    background: white;
    border: 1px solid $primary;
    color: $primary;
  }
}
</style>
