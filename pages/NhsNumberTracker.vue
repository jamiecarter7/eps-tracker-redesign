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
        <h1 class="nhsuk-fieldset__heading">
          Track prescription using NHS Number
        </h1>
      </legend>

      <div class="nhsuk-form-group nhsuk-input--width-10">
        <label class="nhsuk-label" for="address-line-1">
          NHS Number
          <!-- <span class="nhsuk-u-visually-hidden">line 1 of 2</span> -->
        </label>
        <input
          class="nhsuk-input"
          id="address-line-1"
          name="address-line-1"
          type="number"
          maxlength="10"
          oninput="javascript: if (this.value.length > this.maxLength) this.value = this.value.slice(0, this.maxLength);"
        />
      </div>

      <div class="nhsuk-form-group">
        <label class="nhsuk-label" for="address-town"> Date Range </label>
        <div class="nhsuk-hint" id="contact-hint">
          Select a time period or enter a custom date range.
        </div>
        <button
          class="date-range-button"
          :class="{ 'date-range-button-selected': dateRangeSeconds === 86400 }"
          @click="dateRangeSeconds = 86400"
        >
          24 hours
        </button>
        <button
          class="date-range-button"
          :class="{ 'date-range-button-selected': dateRangeSeconds === 604800 }"
          @click="
            dateRangeSeconds = 604800
            todayDateString()
          "
        >
          7 days
        </button>
        <button
          class="date-range-button"
          :class="{
            'date-range-button-selected': dateRangeSeconds === 2419200,
          }"
          @click="dateRangeSeconds = 2419200"
        >
          28 days
        </button>
        <button
          class="date-range-button"
          :class="{
            'date-range-button-selected': dateRangeSeconds === 7776000,
          }"
          @click="dateRangeSeconds = 7776000"
        >
          3 months
        </button>
        <button
          class="date-range-button"
          :class="{
            'date-range-button-selected': dateRangeSeconds === 15552000,
          }"
          @click="dateRangeSeconds = 15552000"
        >
          6 months
        </button>
        <div class="nhsuk-date-input" id="example" style="margin-top: 14px">
          <div class="nhsuk-date-input__item">
            <div class="nhsuk-form-group">
              <input
                class="nhsuk-input nhsuk-input--width-10"
                id="address-town"
                name="address-town"
                type="date"
                v-model="dateFrom"
              />
            </div>
          </div>
          <div class="nhsuk-date-input__item">
            <p>to</p>
          </div>
          <div class="nhsuk-date-input__item">
            <div class="nhsuk-form-group">
              <input
                class="nhsuk-input nhsuk-input--width-10"
                id="address-town"
                name="address-town"
                type="date"
                v-model="dateTo"
              />
            </div>
          </div>
        </div>
      </div>
      <button class="nhsuk-button" type="submit" @click="showResults = true">Search</button>
    </fieldset>
    <results v-if="showResults"/>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data() {
    return {
      dateRangeSeconds: 604800,
      dateTo: '',
      dateFrom: '',
      showResults: false
    }
  },
  watch: {
    dateRangeSeconds() {
      this.dateFrom = this.secondsBeforeNowDateString(this.dateRangeSeconds)
    },
  },
  mounted() {
    this.dateTo = this.todayDateString()
    this.dateFrom = this.secondsBeforeNowDateString(604800)
  },
  methods: {
    todayDateString(): string {
      const date = new Date(Date.now())
      let dateString = date.getFullYear().toString()
      dateString += '-'
      dateString += (date.getMonth() + 1).toString().length === 1
          ? '0' + (date.getMonth() + 1)
          : date.getMonth() + 1
      dateString += '-'
      dateString +=
        date.getDate().toString().length === 1
          ? '0' + date.getDate()
          : date.getDate()
      console.log(dateString)
      return dateString
    },
    secondsBeforeNowDateString(seconds: number): string {
      const date = new Date(Date.now() - seconds * 1000)
      let dateString = date.getFullYear().toString()
      dateString += '-'
      dateString += (date.getMonth() + 1).toString().length === 1
          ? '0' + (date.getMonth() + 1)
          : date.getMonth() + 1
      dateString += '-'
      dateString +=
        date.getDate().toString().length === 1
          ? '0' + date.getDate()
          : date.getDate()
      console.log(dateString)
      return dateString
    },
  },
})
</script>

<style scoped>
.date-range-button {
  background: #005eb8;
  border: none;
  padding: 12px 18px;
  color: white;
  font-size: 20px;
  font-weight: 700;
  margin: 0 10px 10px 0;
}

.date-range-button-selected {
  background: #ffeb3b;
  color: #212b32;
}

/* */
</style>
