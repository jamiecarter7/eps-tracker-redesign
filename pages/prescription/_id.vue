<template>
  <div>
    <!-- <div class="prescriptionCancellation">
      <p class="nhsuk-u-font-size-24 nhsuk-u-font-weight-bold">
        Prescription Pending Cancellation
      </p>
    </div>
    <p>
      The prescriber has requested the cancellation of this prescription, please
      return the prescription to the spine for cancellation.
    </p> -->

    <h1>Prescription Details</h1>
    <!-- <h2 class="">Details</h2> -->
    <dl class="nhsuk-summary-list">
      <div class="nhsuk-summary-list__row">
        <dt class="nhsuk-summary-list__key">Prescription ID</dt>
        <dd class="nhsuk-summary-list__value">
          {{ $route.params.id }} <button class="button-grey">copy</button>
        </dd>
      </div>
      <div class="nhsuk-summary-list__row">
        <dt class="nhsuk-summary-list__key">Prescription Signed</dt>
        <dd class="nhsuk-summary-list__value">30 November 2022</dd>
      </div>
      <div class="nhsuk-summary-list__row">
        <dt class="nhsuk-summary-list__key">Prescription Expiry</dt>
        <dd class="nhsuk-summary-list__value">30 May 2022</dd>
      </div>
      <div class="nhsuk-summary-list__row">
        <dt class="nhsuk-summary-list__key">Prescription Type</dt>
        <dd class="nhsuk-summary-list__value">Repeat Dispensing (3 of 8)</dd>
      </div>
    </dl>
    <!-- <h2>Prescribing Organisation</h2> -->
    <dl class="nhsuk-summary-list">
      <div class="nhsuk-summary-list__row">
        <dt class="nhsuk-summary-list__key">Prescriber Organisation</dt>
        <dd class="nhsuk-summary-list__value">Rise Healthcare (C810761)</dd>
      </div>
      <div class="nhsuk-summary-list__row">
        <dt class="nhsuk-summary-list__key">Prescriber Contact</dt>
        <dd class="nhsuk-summary-list__value">01234 567890</dd>
      </div>
      <div class="nhsuk-summary-list__row">
        <dt class="nhsuk-summary-list__key">Patient NHS Number</dt>
        <dd class="nhsuk-summary-list__value">01234 567890</dd>
      </div>
    </dl>

    <!-- <h2>Dispenser Information</h2> -->
    <dl class="nhsuk-summary-list">
      <div class="nhsuk-summary-list__row">
        <dt class="nhsuk-summary-list__key">Nominated Dispenser</dt>
        <dd class="nhsuk-summary-list__value">Main Street Pharmacy (FJ111)</dd>
      </div>
      <!-- <div class="nhsuk-summary-list__row">
        <dt class="nhsuk-summary-list__key">Dispenser Organisation</dt>
        <dd class="nhsuk-summary-list__value">Main Street Pharmacy (FJ111)</dd>
      </div>
      <div class="nhsuk-summary-list__row">
        <dt class="nhsuk-summary-list__key">Dispenser Contact</dt>
        <dd class="nhsuk-summary-list__value">01234 567890</dd>
      </div> -->
    </dl>

    <!-- <h2>Cancellation Requests</h2> -->
    <dl class="nhsuk-summary-list">
      <div class="nhsuk-summary-list__row">
        <dt class="nhsuk-summary-list__key">Applied Cancellations</dt>
        <dd class="nhsuk-summary-list__value">None</dd>
      </div>
      <div class="nhsuk-summary-list__row">
        <dt class="nhsuk-summary-list__key">Pending Cancellations</dt>
        <dd class="nhsuk-summary-list__value">None</dd>
      </div>
    </dl>

    <h2>Current Prescription Location</h2>
    <!-- <div class="prescriptionDownloaded"> -->
    <dl class="nhsuk-summary-list">
      <div class="nhsuk-summary-list__row">
        <dt class="nhsuk-summary-list__key">Organisation</dt>
        <dd class="nhsuk-summary-list__value">
          <a v-if="status.name === 'dispensed'" href="#"
            >Main Street Pharmacy (FJ111)</a
          >
          <a
            v-else-if="
              status.name !== 'on spine' && status.name !== 'cancelled'
            "
            href="#"
            >Bankside Chemist (FZ112)</a
          >

          <template v-else>NHS Spine</template>
        </dd>
      </div>
      <div
        class="nhsuk-summary-list__row"
        v-if="status.name !== 'on spine' && status.name !== 'cancelled'"
      >
        <dt class="nhsuk-summary-list__key">Organisation Address</dt>
        <dd
          v-if="status.name === 'dispensed'"
          class="nhsuk-summary-list__value"
        >
          135 Main Street, High Newbury
        </dd>
        <dd v-else class="nhsuk-summary-list__value">
          1 Bankside Street, Bankington
        </dd>
      </div>
      <div
        class="nhsuk-summary-list__row"
        v-if="status.name !== 'on spine' && status.name !== 'cancelled'"
      >
        <dt class="nhsuk-summary-list__key">Organisation Contact</dt>
        <dd class="nhsuk-summary-list__value">01234 567890</dd>
      </div>
      <div class="nhsuk-summary-list__row">
        <dt class="nhsuk-summary-list__key">Presciption Status</dt>
        <dd class="nhsuk-summary-list__value">
          <strong class="nhsuk-tag" :class="`nhsuk-tag--` + status.color">{{
            status.name
          }}</strong>
        </dd>
      </div>
    </dl>

    <h2>Prescription Event History</h2>
    <table role="table" class="nhsuk-table-responsive">
      <caption class="nhsuk-table__caption">
        Details of event history
      </caption>
      <thead role="rowgroup" class="nhsuk-table__head">
        <tr role="row">
          <th role="columnheader" class="" scope="col">Prescription Message</th>
          <th role="columnheader" class="" scope="col">Date/Time</th>
          <th role="columnheader" class="" scope="col">Organisation</th>
          <th role="columnheader" class="" scope="col">Status</th>
        </tr>
      </thead>
      <tbody class="nhsuk-table__body">
        <tr role="row" class="nhsuk-table__row">
          <td role="cell" class="nhsuk-table__cell">
            <!-- <nuxt-link :to="'prescription/"> -->
            <span class="nhsuk-table-responsive__heading"
              >Prescription Message </span
            >Prescription upload successful
            <!-- </nuxt-link> -->
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Date/Time </span
            >13-Nov-2021 10:34:29
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <nuxt-link to="#">
              <span class="nhsuk-table-responsive__heading">Organisation </span
              >C810761
            </nuxt-link>
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Status </span
            ><strong class="nhsuk-tag nhsuk-tag--blue">on spine</strong>
          </td>
        </tr>

        <tr
          role="row"
          class="nhsuk-table__row"
          v-if="status.name !== 'on spine'"
        >
          <td role="cell" class="nhsuk-table__cell">
            <!-- <nuxt-link :to="'prescription/"> -->
            <span class="nhsuk-table-responsive__heading"
              >Prescription Message </span
            >Nominated release request successful
            <!-- </nuxt-link> -->
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Date/Time </span
            >13-Nov-2021 11:02:56
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <nuxt-link to="#">
              <span class="nhsuk-table-responsive__heading">Organisation </span
              >FJ111
            </nuxt-link>
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Status </span
            ><strong class="nhsuk-tag nhsuk-tag--purple">with dispenser</strong>
          </td>
        </tr>

        <tr
          role="row"
          class="nhsuk-table__row"
          v-if="status.name !== 'on spine'"
        >
          <td role="cell" class="nhsuk-table__cell">
            <!-- <nuxt-link :to="'prescription/"> -->
            <span class="nhsuk-table-responsive__heading"
              >Prescription Message </span
            >Dispense notification success
            <!-- </nuxt-link> -->
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Date/Time </span
            >13-Nov-2021 11:05:21
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <nuxt-link to="#">
              <span class="nhsuk-table-responsive__heading">Organisation </span
              >FJ111
            </nuxt-link>
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Status </span
            ><strong class="nhsuk-tag nhsuk-tag--yellow">dispensed</strong>
          </td>
        </tr>

        <tr
          role="row"
          class="nhsuk-table__row"
          v-if="status.name !== 'on spine' && status.name !== 'dispensed'"
        >
          <td role="cell" class="nhsuk-table__cell">
            <!-- <nuxt-link :to="'prescription/"> -->
            <span class="nhsuk-table-responsive__heading"
              >Prescription Message </span
            >Prescription return success
            <!-- </nuxt-link> -->
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Date/Time </span
            >13-Nov-2021 13:08:27
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <nuxt-link to="#">
              <span class="nhsuk-table-responsive__heading">Organisation </span
              >C810761
            </nuxt-link>
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Status </span
            ><strong class="nhsuk-tag nhsuk-tag--blue">on spine</strong>
          </td>
        </tr>

        <tr
          role="row"
          class="nhsuk-table__row"
          v-if="
            status.name !== 'on spine' &&
            status.name !== 'cancelled' &&
            status.name !== 'dispensed'
          "
        >
          <td role="cell" class="nhsuk-table__cell">
            <!-- <nuxt-link :to="'prescription/"> -->
            <span class="nhsuk-table-responsive__heading"
              >Prescription Message </span
            >Presciption release request successful
            <!-- </nuxt-link> -->
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Date/Time </span
            >13-Nov-2021 13:09:04
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <nuxt-link to="#">
              <span class="nhsuk-table-responsive__heading">Organisation </span
              >FZ112
            </nuxt-link>
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Status </span
            ><strong class="nhsuk-tag nhsuk-tag--purple">with dispenser</strong>
          </td>
        </tr>

        <tr
          role="row"
          class="nhsuk-table__row"
          v-if="
            status.name !== 'on spine' &&
            status.name !== 'with dispenser' &&
            status.name !== 'cancelled' &&
            status.name !== 'dispensed'
          "
        >
          <td role="cell" class="nhsuk-table__cell">
            <!-- <nuxt-link :to="'prescription/"> -->
            <span class="nhsuk-table-responsive__heading"
              >Prescription Message </span
            >Dispense notification success
            <!-- </nuxt-link> -->
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Date/Time </span
            >13-Nov-2021 13:09:56
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <nuxt-link to="#">
              <span class="nhsuk-table-responsive__heading">Organisation </span
              >FZ112
            </nuxt-link>
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Status </span
            ><strong class="nhsuk-tag nhsuk-tag--yellow">dispensed</strong>
          </td>
        </tr>

        <tr
          role="row"
          class="nhsuk-table__row"
          v-if="
            status.name !== 'on spine' &&
            status.name !== 'with dispenser' &&
            status.name !== 'cancelled' &&
            status.name !== 'dispensed'
          "
        >
          <td role="cell" class="nhsuk-table__cell">
            <!-- <nuxt-link :to="'prescription/"> -->
            <span class="nhsuk-table-responsive__heading"
              >Prescription Message </span
            >Claim request success
            <!-- </nuxt-link> -->
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Date/Time </span
            >14-Nov-2021 09:38:47
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <nuxt-link to="#">
              <span class="nhsuk-table-responsive__heading">Organisation </span
              >FZ112
            </nuxt-link>
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Status </span
            ><strong class="nhsuk-tag nhsuk-tag--green">claimed</strong>
          </td>
        </tr>

        <tr
          role="row"
          class="nhsuk-table__row"
          v-if="
            status.name !== 'on spine' &&
            status.name !== 'claimed' &&
            status.name !== 'with dispenser' &&
            status.name !== 'dispensed'
          "
        >
          <td role="cell" class="nhsuk-table__cell">
            <!-- <nuxt-link :to="'prescription/"> -->
            <span class="nhsuk-table-responsive__heading"
              >Prescription Message </span
            >Prescription cancellation request success
            <!-- </nuxt-link> -->
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Date/Time </span
            >13-Nov-2021 13:08:27
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <nuxt-link to="#">
              <span class="nhsuk-table-responsive__heading">Organisation </span
              >FZ112
            </nuxt-link>
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Status </span
            ><strong class="nhsuk-tag nhsuk-tag--red">cancelled</strong>
          </td>
        </tr>
      </tbody>
    </table>

    <!-- <td role="cell" class="nhsuk-table__cell">
      <span class="nhsuk-table-responsive__heading">Status </span
      ><strong class="nhsuk-tag" :class="`nhsuk-tag--` + result.status.color">{{
        result.status.name
      }}</strong>
    </td> -->
    <!-- </div> -->
    <!-- <div class="prescriptionDownloaded"> -->
    <!-- <p class="nhsuk-u-font-size-22 nhsuk-u-font-weight-bold pReducedPadding">
        Peak Pharmacy - FCF30
      </p>
      <p class="nhsuk-u-font-size-22 pReducedPadding">
        1 Burton Road, Derby, DE1 1TH
      </p>
      <p class="nhsuk-u-font-size-22 pReducedPadding">01332 342279</p>
      <p class="p0Padding">
        <strong class="nhsuk-tag nhsuk-tag--yellow">Dispensed</strong>
      </p> -->
    <!-- </div> -->

    <!-- <h2>Prescription Location</h2>
    <div class="prescriptionDownloaded">
      <p class="nhsuk-u-font-size-32 nhsuk-u-font-weight-bold pReducedPadding">Awaiting download</p>
      <p class="nhsuk-u-font-size-22 pReducedPadding">NHS Spine</p>
      <p class="nhsuk-u-font-size-22 p0Padding">{{id}}</p>
    </div> -->
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data() {
    return {
      rxInfo: { desc: 'Prescription Id', data: this.$route.params.id },
      status: {} as { name: string; color: string },
      statusOptions: [
        { name: 'claimed', color: 'green' },
        { name: 'cancelled', color: 'red' },
        { name: 'on spine', color: 'blue' },
        { name: 'with dispenser', color: 'purple' },
        { name: 'dispensed', color: 'yellow' },
      ] as Array<{ name: string; color: string }>,
    }
  },
  mounted() {
    // if (this.$route.query.status === undefined) {
    this.createStatus()
    // } else {
    //   for (const statusObjCheck of this.statusOptions) {
    //     if (statusObjCheck.name as string === this.$route.query) {
    //       this.status === statusObjCheck
    //     }
    //   }
    // }
  },
  methods: {
    createStatus(): void {
      this.status =
        this.statusOptions[this.getRandomInt(this.statusOptions.length)]
    },
    getRandomInt(max: number): number {
      return Math.floor(Math.random() * max)
    },
  },
})
</script>

<style scoped>
.prescriptionDownloaded {
  background: #ffffff;
  padding: 24px 30px;
  margin-bottom: 40px;
}

.prescriptionCancellation {
  background: #d5281b;
  padding: 20px 30px;
  color: #fff;
  margin-bottom: 30px;
}

.prescriptionCancellation p {
  margin-bottom: 0;
}
.hr {
  margin: -18px 0 16px;
}

.pReducedPadding {
  margin-bottom: 8px;
}
.p0Padding {
  margin-bottom: 0px;
}

.button-grey {
  background: #c7c7c7;
  border: none;
  font-weight: 600;
  padding: 4px 10px;
  margin-left: 10px;
  text-transform: uppercase;
}

.button-grey:hover {
  background: rgb(150, 202, 156);
}
</style>
