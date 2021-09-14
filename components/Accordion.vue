<template>
  <div :id="accordionID" class="accordion">
    <div class="accordion-item">
      <h2 :id="accordionID2" class="accordion-header">
        <button
          class="accordion-button collapsed"
          type="button"
          data-bs-toggle="collapse"
          :data-bs-target="`#${accordionCollapseID}`"
          aria-expanded="false"
          :aria-controls="accordionCollapseID"
        >
          {{ title }}
        </button>
      </h2>
      <div
        :id="accordionCollapseID"
        class="accordion-collapse collapse space"
        :aria-labelledby="accordionID2"
        :data-bs-parent="`#${accordionID}`"
      >
        <div class="accordion-body">
        <br />
         {{ content }}
         <br /><br />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Accordion',
  props: {
    accordionID: {
      type: String,
      default: ''
    },
    accordionID2: {
      type: String,
      default: ''
    },
    accordionCollapseID: {
      type: String,
      default: ''
    },
    title: {
      type: String,
      default: ''
    },
    content: {
      type: String,
      default: ''
    },
    accordionHeading: {
      type: String,
      default: ''
    }
  }
}
</script>

<style lang="scss" scoped>
.space {
 @media (min-width: 800px) {
    padding-right: 200px !important;
    padding-left: 30px !important;
 }
}
.accordion-button {
  font-style: normal;
  font-weight: normal;
  font-size: 12px;
  line-height: 19px;
  letter-spacing: 0.02em;
  color: #020304;
  padding-left: 50px;
}
.accordion-body {
  font-style: normal;
  font-weight: normal;
  font-size: 12px;
  line-height: 26px;
  letter-spacing: 0.02em;
}
</style>
