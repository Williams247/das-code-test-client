<template>
  <div class="first-layout">
    <div id="authenticiated-navbar">
      <nav class="navbar navbar-expand-lg p-t-b">
        <div class="container-fluid">
          <div class="navbar-brand primary-color">
            Skills Village
          </div>
          <button
            class="navbar-toggler"
            type="button"
            data-bs-toggle="collapse"
            data-bs-target="#navbarTogglerDemo03"
            aria-controls="navbarTogglerDemo03"
            aria-expanded="false"
            aria-label="Toggle navigation"
          >
            <font-awesome-icon :icon="['fas', 'bars']" />
          </button>
          <div id="space-menu" class="space-menu" />
          <div id="navbarTogglerDemo03" class="collapse navbar-collapse">
            <ul class="navbar-nav me-auto mb-2 mb-lg-0 pt-1">
              <li class="nav-item pt-1">
                <nuxt-link to="">
                  Home
                </nuxt-link>
              </li>
              <li class="nav-item pt-1">
                <nuxt-link to="">
                  Courses
                </nuxt-link>
              </li>
              <li class="nav-item pt-1">
                <nuxt-link to="">
                  FAQs
                </nuxt-link>
              </li>
              <li class="nav-item pt-1">
                <nuxt-link to="">
                  Contact
                </nuxt-link>
              </li>
              <li class="nav-item pt-1">
                <nuxt-link to="">
                  Login
                </nuxt-link>
              </li>
              <li id="list-special">
                <action-button
                  variant="primary-outline"
                  action-button-type="button"
                  measurement="nav-btn"
                  label="Get Started"
                />
              </li>
            </ul>
          </div>
        </div>
      </nav>
    </div>
    <div>
      <Nuxt />
    </div>
    <footer class="d-flex justify-content-center pb-5">
      <div class="col-lg-10 d-flex flex-direction-row-column">
        <div class="col-lg-3">
          <div id="skills-village">Skills Village</div>
          <div class="d-flex mt-4 pt-2">
            <div class="i-p">
              <instagram variant="light" />
            </div>
            <div class="px-2">
              <facebook variant="light" />
            </div>
            <div class="px-2">
              <twitter variant="light" />
            </div>
            <div class="px-2">
              <linkendin variant="light" />
            </div>
          </div>
        </div>
        <div class="col-lg-2">
          <div class="footer-links pb-4">
            Quick Links
          </div>
          <ul v-for="i in footerLinks.quick_links" :key="i" class="pt-1">
            <nuxt-link :to="i.url">
              <li>{{ i.label }}</li>
            </nuxt-link>
          </ul>
        </div>
        <div class="col-lg-2">
          <div class="footer-links pb-4">
            About
          </div>
          <ul v-for="i in footerLinks.about" :key="i" class="pt-1">
            <nuxt-link :to="i.url">
              <li>{{ i.label }}</li>
            </nuxt-link>
          </ul>
        </div>
        <div class="col-lg-3">
          <div class="footer-links pb-4">
            Conact
          </div>
          <ul v-for="i in footerLinks.contact" :key="i" class="pt-1">
            <nuxt-link :to="i.url">
              <li>{{ i.label }}</li>
            </nuxt-link>
          </ul>
        </div>
        <div class="col-lg-2">
          <div class="footer-links">
            Skill village for mobile
          </div>

          <div class="col-lg-12 mt-3 pt-3 store-button">
            <apple-play-store-button />
          </div>
          <div class="col-lg-12 mt-3 store-button">
            <google-play-store-button />
          </div>
        </div>
        <!--end of line-->
      </div>
    </footer>
  </div>
</template>

<script>
import footerLinks from '../constants/footer.json'
export default {
  name: 'Default_Layout',
  data () {
    return {
      footerLinks
    }
  }
}
</script>

<style lang="scss" scoped>
#list-special {
  @media (min-width: 800px) {
    width: 130px;
    padding-left: 5px;
  }
}
.navbar {
  background: #eff3fa;
}

.p-t-b {
  @media (min-width: 800px) {
    padding-top: 30px !important;
    padding-bottom: 30px !important;
  }
}

#space-menu {
  width: 40%;
}

footer {
  background: #1B0630;
  padding-top: 80px;
  #skills-village {
    color: white;
    font-style: normal;
    font-weight: bold;
    font-size: 16px;
    line-height: 25px;
  }
  .i-p {
    padding-right: 6px;
  }
  .footer-links {
    font-style: normal;
    font-size: 16px;
    line-height: 19px;
    text-transform: capitalize;
    color: white;
  }
  ul {
    margin-left: -28px;
    li {
      font-style: normal;
      font-weight: normal;
      font-size: 16px;
      line-height: 19px;
      color: #FFFFFF;
    }
  }
}

.store-button {
  @media (min-width: 800px) {
    margin-left: -6px;
  }
}
</style>
