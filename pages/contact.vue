<template>
  <div id="contact-page" class="second-layout py-5">
    <div class="d-flex justify-content-center py-5">
      <div id="contact-container" class="pb-5">
        <div id="pane-container" class="d-flex flex-direction-row-column">
          <div class="col-lg-6">
            <div id="contact-desc">
              We would love to hear<br />
              from you
            </div>
            <div id="contact-desc-2" class="mt-3">
              Follow us on our social media platforms <br />
              or drop us a message by filling the form
            </div>
            <div>
              <div class="d-flex mt-3 pt-1">
                <div class="i-p">
                  <instagram variant="dark" size="17" />
                </div>
                <div class="px-2">
                  <facebook variant="dark" size="17" />
                </div>
                <div class="px-2">
                  <twitter variant="dark" size="17" />
                </div>
                <div class="px-2">
                  <linkendin variant="dark" size="17" />
                </div>
              </div>
              <div class="mt-5">
                <img id="contact-info" src="/images/contact-info.png" />
              </div>
            </div>
          </div>
          <div class="col-lg-6">
            <div class="card remove-card-border py-4">
              <div class="px-4 py-4">
                <form>
                  <div class="d-flex flex-direction-row-column">
                    <div class="col-lg-5 px-3">
                      <input
                        type="text"
                        class="form-control py-3"
                        placeholder="First Name"
                      />
                    </div>
                    <div class="col-lg-7 px-3">
                      <input
                        type="text"
                        class="form-control py-3"
                        placeholder="Last Name"
                      />
                    </div>
                  </div>
                  <div class="col-lg-12 mt-4 px-3 pt-2">
                    <input
                      type="email"
                      placeholder="Email Address"
                      class="form-control py-3"
                    />
                  </div>
                  <div class="col-lg-12 mt-4 px-3 pt-2">
                    <input
                      type="number"
                      placeholder="Phone Number"
                      class="form-control py-3"
                    />
                  </div>
                  <div class="col-lg-12 mt-4 px-3 pt-2">
                    <textarea
                      class="form-control py-3"
                      placeholder="Your Message"
                    ></textarea>
                  </div>
                  <div class="col-lg-5 px-3">
                    <action-button
                      action-button-type="submit"
                      variant="primary"
                      :loading="loading"
                      :label="loading ? 'Loading...' : 'Submit'"
                      measurement="py-2 mt-5 round"
                    />
                  </div>
                </form>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Contact',
  data () {
    return {
      loading: false
    }
  }
}
</script>

<style lang="scss" scoped>
#contact-container {
  width: 86.5%;
  #pane-container {
    @media (min-width: 800px) {
      padding-bottom: 100px;
    }
  }
  #contact-desc {
    font-family: Inria Serif;
    font-style: normal;
    font-weight: bold;
    font-size: 45px;
    line-height: 110.4%;
    color: #000000;
  }
  #contact-desc-2 {
    font-style: normal;
    font-weight: 300;
    font-size: 16px;
    line-height: 146.02%;
    color: #000000;
  }
  #contact-info {
    width: 70%;
  }
}

input[type="text"],
input[type="email"],
input[type="number"],
textarea {
  text-indent: 10px;
  box-sizing: border-box;
  border-radius: 4px;
}

textarea {
  height: 150px;
  resize: none;
}
</style>
