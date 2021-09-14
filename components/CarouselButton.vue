<template>
    <button id="carousel-button" class="btn">
        <div v-if="arrowPosition === 'left'">
            <left-arrow-icon />
        </div>
        <div v-if="arrowPosition === 'right'">
            <right-arrow-icon />
        </div>
    </button>
</template>

<script>
import LeftArrowIcon from './LeftArrowIcon.vue'
import RightArrowIcon from './RightArrowIcon.vue'
export default {
  name: 'RightArrowCarouselButton',
  props: {
    arrowPosition: {
      type: String,
      default: ''
    }
  },
  components: {
    LeftArrowIcon,
    RightArrowIcon
  }
}
</script>

<style lang="scss" scoped>
@import '~/assets/css/index.scss';

#carousel-button {
  background: $primary;
  border-radius: 50%;
  width: 43px;
  height: 43px;
}
</style>
