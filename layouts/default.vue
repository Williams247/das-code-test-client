<template>
  <div id="unauthenticiated-layout">
    <div id="unauthenticiated-navbar">
      <nav class="navbar navbar-expand-lg py-4">
        <div class="container-fluid">
          <div class="navbar-brand primary-color">Skills Village</div>
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
          <div class="col-lg-8 space-menu"></div>
          <div class="collapse navbar-collapse" id="navbarTogglerDemo03">
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
              <li class="nav-item">
                <nuxt-link to>Home</nuxt-link>
              </li>
              <li class="nav-item">
                <nuxt-link to>Courses</nuxt-link>
              </li>
              <li class="nav-item">
                <nuxt-link to>FAQs</nuxt-link>
              </li>
              <li class="nav-item">
                <nuxt-link to>Contact</nuxt-link>
              </li>
            </ul>
          </div>
        </div>
      </nav>
    </div>
    <div class="layout-space">
      <Nuxt />
    </div>
  </div>
</template>

<style lang="scss" scoped>
#unauthenticiated-layout {
  background-image: linear-gradient(50deg, #a8a0af, #dceaf6, #dceaf6);
}
.navbar-brand {
  font-style: normal;
  font-weight: bold;
  font-size: 21px;
  line-height: 25px;
}
</style>
