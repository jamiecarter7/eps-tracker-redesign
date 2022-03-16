<template>
  <div>
    <div class="nhsuk-back-link">
      <a class="nhsuk-back-link__link" href="#">
        <svg
          class="nhsuk-icon nhsuk-icon__chevron-left"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
          aria-hidden="true"
          height="24"
          width="24"
        >
          <path
            d="M8.5 12c0-.3.1-.5.3-.7l5-5c.4-.4 1-.4 1.4 0s.4 1 0 1.4L10.9 12l4.3 4.3c.4.4.4 1 0 1.4s-1 .4-1.4 0l-5-5c-.2-.2-.3-.4-.3-.7z"
          ></path>
        </svg>
        Go back</a
      >
    </div>
    <fieldset class="nhsuk-fieldset">
      <legend class="nhsuk-fieldset__legend nhsuk-fieldset__legend--l">
        <h1 class="nhsuk-fieldset__heading">Search prescription by ID</h1>
      </legend>

      <div class="nhsuk-form-group">
        <label class="nhsuk-label" for="address-line-1">
          Prescription ID
          <span class="nhsuk-u-visually-hidden">line 1 of 2</span>
        </label>
        <input
          class="nhsuk-input"
          id="address-line-1"
          name="address-line-1"
          type="text"
        />
      </div>
      <button class="nhsuk-button" type="submit" @click="findRx()">
        Search
      </button>
    </fieldset>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  methods: {
    createRandomPrescriptionID(): string {
      let thisString = ''
      thisString += Math.random()
        .toString(36)
        .replace(/[^a-z]+/g, '')
        .substr(0, 5)
      thisString += '-'
      thisString += 'c100271'
      thisString += '-'
      thisString += Math.random()
        .toString(36)
        .replace(/[^a-z]+/g, '')
        .substr(0, 5)
      return thisString.toUpperCase()
    },
    findRx() {
      this.$router.push('/prescription/' + this.createRandomPrescriptionID())
    }
  },
})
</script>
