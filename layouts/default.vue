<template>
  <div>
    <a class="nhsuk-skip-link" href="#maincontent">Skip to main content</a>

    <Header />
    <div class="nhsuk-width-container">
      <main class="nhsuk-main-wrapper" id="maincontent" role="main">
        <Nuxt />
      </main>
    </div>
    <footer role="contentinfo">
      <div id="nhsuk-footer" class="nhsuk-footer">
        <div class="nhsuk-width-container">
          <p>Version: R.12.v34</p>
          <p class="nhsuk-footer__copyright">&copy; Crown copyright</p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({})
</script>
