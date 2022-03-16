<template>
  <div>
    <!-- <main class="nhsuk-main-wrapper" id="maincontent" role="main"> -->
    <h1>NHS Prescription Tracker</h1>
    <p>
      The NHS prescription tracker allows you to track the location and status
      information of digital prescriptions.
    </p>
    <div class="nhsuk-grid-row">
      <div class="nhsuk-grid-column-one-half">
        <div class="nhsuk-card nhsuk-card--clickable">
          <div class="nhsuk-card__content">
            <h2 class="nhsuk-card__heading nhsuk-heading-m">
              <a class="nhsuk-card__link" href="/nhsnumbertracker"
                >Track using NHS number</a
              >
            </h2>
            <p class="nhsuk-card__description">
              Search for prescriptions issued for a specific patient using their
              unique NHS number.
            </p>
          </div>
        </div>
      </div>
      <div class="nhsuk-grid-column-one-half">
        <div class="nhsuk-card nhsuk-card--clickable">
          <div class="nhsuk-card__content">
            <h2 class="nhsuk-card__heading nhsuk-heading-m">
              <a class="nhsuk-card__link" href="/idtracker"
                >Track using Prescription ID</a
              >
            </h2>
            <p class="nhsuk-card__description">
              Search for a prescription using the prescription ID (prescription
              barcode)
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({})
</script>
