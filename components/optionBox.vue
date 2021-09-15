<template>
  <div>
    <button
      :class="[isClicked && possibleSum === possibleSum ? 'btn mt-3 text-center py-4 show-number':'btn option-box mt-3 text-center py-4']"
      @click="handleShowNumber"
      @blur="handleHideNumber"
    >
      {{ isClicked && possibleSum === possibleSum ? possibleSum : '?' }}
    </button>
  </div>
</template>

<script>
export default {
  name: 'OptionBox',
  props: {
    possibleSum: {
      type: Number,
      default: 0
    }
  },
  data () {
    return {
      isClicked: false
    }
  },
  methods: {
    handleShowNumber () {
      this.isClicked = true
    },
    handleHideNumber () {
      this.isClicked = false
    }
  }
}
</script>

<style lang="scss" scoped>
.option-box {
  background: #3f977d;
  border: 1.5px solid #969696;
  box-sizing: border-box;
  width: 142px;
  font-style: normal;
  font-weight: normal;
  font-size: 45px;
  line-height: 53px;
  color: #E9E6E6;
  cursor: pointer;
  border-radius: 0 !important;
  &:hover {
    background: #327763;
  }
}

.show-number {
  background: #D36262;
  border: 1.5px solid #969696;
  box-sizing: border-box;
  width: 142px;
  font-style: normal;
  font-weight: normal;
  font-size: 45px;
  line-height: 53px;
  color: #E9E6E6;
  cursor: pointer;
  border-radius: 0 !important;
  &:hover {
    background: #bd4d4d;
  }
}
</style>
