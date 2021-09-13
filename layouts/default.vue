<template>
  <div class="first-layout">
    <div id="unauthenticiated-navbar">
      <nav class="navbar navbar-expand-lg py-4">
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
          <div class="col-lg-7 space-menu" />
          <div id="navbarTogglerDemo03" class="collapse navbar-collapse">
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
              <li class="nav-item">
                <nuxt-link to="">
                  Home
                </nuxt-link>
              </li>
              <li class="nav-item">
                <nuxt-link to="">
                  Courses
                </nuxt-link>
              </li>
              <li class="nav-item">
                <nuxt-link to="">
                  FAQs
                </nuxt-link>
              </li>
              <li class="nav-item">
                <nuxt-link to="">
                  Contact
                </nuxt-link>
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
