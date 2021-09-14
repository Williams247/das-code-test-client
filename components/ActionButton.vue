<template>
  <div>
    <button
      v-if="variant === 'primary'"
      :type="actionButtonType"
      :disabled="loading"
      :class="`text-center btn primary-button ${measurement}`"
    >
      <span
        v-if="loading"
        class="spinner-border spinner-border-sm"
        role="status"
        aria-hidden="true"
      />
      {{ label }}
    </button>
    <button
      v-if="variant === 'primary-outline'"
      :type="actionButtonType"
      :disabled="loading"
      :class="`text-center btn primary-button-outline ${measurement}`"
    >
      <span
        v-if="loading"
        class="spinner-border spinner-border-sm"
        role="status"
        aria-hidden="true"
      />
      {{ label }}
    </button>
     <button
      v-if="variant === 'dark-outline'"
      :type="actionButtonType"
      :disabled="loading"
      :class="`text-center btn dark-button-outline ${measurement}`"
    >
      <span
        v-if="loading"
        class="spinner-border spinner-border-sm"
        role="status"
        aria-hidden="true"
      />
      {{ label }}
    </button>
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
.primary-button {
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

.primary-button-outline {
  background: transparent;
  border-radius: 15px;
  width: 100%;
  color: $primary;
  border: 1px solid $primary;
  &:hover {
    background: $primary;
    color: white;
  }
}

.dark-button-outline {
  background: transparent;
  border-radius: 15px;
  width: 100%;
  color: black;
  border: 1px solid gray;
  &:hover {
    background: $primary;
    color: white;
  }
}
</style>
