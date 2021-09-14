<template>
  <div>
    <div id="first-container" class="d-flex justify-content-center py-5">
      <div class="faq-container mt-5">
        <div id="faqs-desc" class="text-center">Frequently asked questions</div>
        <div class="d-flex flex-direction-row-column justify-content-center mt-5 col-lg-12">
          <div v-for="i in faqData" :key="i" id="faq-button-container" class="col-lg-2 px-2">
            <div>
                <action-button
                  :label="i.label"
                  :actionButtonType="button"
                  measurement="col-lg-12 round"
                  variant="dark-outline"
                />
            </div>
          </div>
        </div>
      </div>
    </div>
    <div id="second-container" class="d-flex justify-content-center py-5">
        <div class="faq-container px-2">
            <div class="card remove-card-border card-dark-shadow py-4 card-top-space accordion-card">
                <div v-for="i in accordionData" :key="i.id" class="px-5 mt-4">
                    <div class="col-lg-11">
                        <accordion
                            :accordionID="`accordion-id-${i.id}`"
                            :accordionID2="`accordion-id-2-${i.id}`"
                            :accordionCollapseID="`accordion-collapse-id-${i.id}`"
                            :accordion-heading-ID="`accordion-heading-id-${i.id}`"
                            :title="i.title"
                            :content="i.body"
                        />
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div id="third-container" class="d-flex justify-content-center">
        <div>
        <div id="question-head">
            Still have questions?
        </div>
        <div id="question-text" class="text-center mt-2 pt-3">
            If you cannot find your answer in our FAQ, you can always<br />
            <nuxt-link to="/contact">contact us.</nuxt-link> We will answer to you shortly
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
      accordionData
    }
  }
}
</script>

<style lang="scss" scoped>
@import "~/assets/css/index.scss";
.faq-container {
    width: 86.5%;
}

#first-container {
  background: $layout-background;
  #faqs-desc {
    font-family: Inria Serif;
    font-style: normal;
    font-weight: bold;
    font-size: 36px;
    line-height: 43px;
    color: #000000;
  }
  #faq-button-container {
    padding-bottom: 100px;
  }
}

#second-container {
   background: $layout-background-2;
}

.card-top-space {
  padding-top: 80px !important;
  padding-bottom: 80px !important;
}

.accordion-card {
  @media (min-width: 800px) {
    margin-top: -130px;
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
</style>
