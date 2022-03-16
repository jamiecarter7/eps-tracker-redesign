<template>
  <div style="margin-top: 20px">
    <table role="table" class="nhsuk-table-responsive">
      <caption class="nhsuk-table__caption">
        Search Results
      </caption>
      <thead role="rowgroup" class="nhsuk-table__head">
        <tr role="row">
          <th role="columnheader" class="" scope="col">Prescription ID</th>
          <th role="columnheader" class="" scope="col">Issue Date</th>
          <th role="columnheader" class="" scope="col">Prescription Type</th>
          <th role="columnheader" class="" scope="col">Location</th>
          <th role="columnheader" class="" scope="col">Status</th>
        </tr>
      </thead>
      <tbody class="nhsuk-table__body">
        <tr
          v-for="(result, index) in results"
          :key="index"
          role="row"
          class="nhsuk-table__row"
        >
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Prescription ID </span
            ><nuxt-link :to="'prescription/' + result.rxId"
              >{{ result.rxId }}
            </nuxt-link><button class="button-grey" @click.prevent="copy(result.rxId)" :ref="result.rxId">copy id</button>
            <!-- <button class="button-grey">copy id</button> -->
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Issue Date </span
            >13-Nov-2021
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading"
              >Prescription Type </span
            >Acute
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Organisation </span
            ><nuxt-link to="#">FJ111 </nuxt-link>
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Status </span
            ><strong
              class="nhsuk-tag"
              :class="`nhsuk-tag--` + result.status.color"
              >{{ result.status.name }}</strong
            >
          </td>
        </tr>

        <!-- <tr role="row" class="nhsuk-table__row">
          <td role="cell" class="nhsuk-table__cell">
            <a
              ><span class="nhsuk-table-responsive__heading"
                >Prescription ID </span
              >AAAAAA-C10000-BBBBBB
            </a>
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Issue Date </span
            >13-Nov-2021
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading"
              >Prescription Type </span
            >Acute
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Status </span
            ><strong class="nhsuk-tag nhsuk-tag--yellow">Dispensed</strong>
          </td>
        </tr>


        <tr role="row" class="nhsuk-table__row">
          <td role="cell" class="nhsuk-table__cell">
            <a
              ><span class="nhsuk-table-responsive__heading"
                >Prescription ID </span
              >AAAAAA-C10000-BBBBBB
            </a>
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Issue Date </span
            >13-Nov-2021
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading"
              >Prescription Type </span
            >Acute
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Status </span
            ><strong class="nhsuk-tag nhsuk-tag--purple">With dispenser</strong>
          </td>
        </tr>


        <tr role="row" class="nhsuk-table__row">
          <td role="cell" class="nhsuk-table__cell">
            <a
              ><span class="nhsuk-table-responsive__heading"
                >Prescription ID </span
              >ABBBAA-C10000-BCCEBG
            </a>
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Issue Date </span
            >27-Oct-2021
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading"
              >Prescription Type </span
            >Repeat
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Status </span
            ><strong class="nhsuk-tag nhsuk-tag--blue">On Spine</strong>
          </td>
        </tr>

        <tr role="row" class="nhsuk-table__row">
          <td role="cell" class="nhsuk-table__cell">
            <a
              ><span class="nhsuk-table-responsive__heading"
                >Prescription ID </span
              >ACCCAA-C10000-BCCDDD
            </a>
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Issue Date </span
            >20-Oct-2021
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading"
              >Prescription Type </span
            >Acute
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Status </span
            ><strong class="nhsuk-tag nhsuk-tag--red">Cancelled</strong>
          </td>
        </tr>
        <tr role="row" class="nhsuk-table__row">
          <td role="cell" class="nhsuk-table__cell">
            <a
              ><span class="nhsuk-table-responsive__heading"
                >Prescription ID </span
              >ACCCAA-C10000-BCCDDD
            </a>
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Issue Date </span
            >20-Oct-2021
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading"
              >Prescription Type </span
            >Acute
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Status </span
            ><strong class="nhsuk-tag nhsuk-tag--green">Claimed</strong>
          </td>
        </tr>
        <tr role="row" class="nhsuk-table__row">
          <td role="cell" class="nhsuk-table__cell">
            <a
              ><span class="nhsuk-table-responsive__heading"
                >Prescription ID </span
              >ACCCAA-C10000-BCCDDD
            </a>
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Issue Date </span
            >20-Oct-2021
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading"
              >Prescription Type </span
            >Acute
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Status </span
            ><strong class="nhsuk-tag nhsuk-tag--green">Claimed</strong>
          </td>
        </tr>
        <tr role="row" class="nhsuk-table__row">
          <td role="cell" class="nhsuk-table__cell">
            <a
              ><span class="nhsuk-table-responsive__heading"
                >Prescription ID </span
              >ACCCAA-C10000-BCCDDD
            </a>
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Issue Date </span
            >20-Oct-2021
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading"
              >Prescription Type </span
            >Acute
          </td>
          <td role="cell" class="nhsuk-table__cell">
            <span class="nhsuk-table-responsive__heading">Status </span
            ><strong class="nhsuk-tag nhsuk-tag--green">Claimed</strong>
          </td>
        </tr> -->
      </tbody>
    </table>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data() {
    return {
      results: [] as Array<object>,
      test: '' as string,
      statusOptions: [
        { name: 'claimed', color: 'green' },
        { name: 'cancelled', color: 'red' },
        { name: 'on spine', color: 'blue' },
        { name: 'with dispenser', color: 'purple' },
        { name: 'dispensed', color: 'yellow' },
      ] as Array<object>,
      // furthestDate: Date.now()
      // statusColors: [{status: }]
    }
  },
  mounted() {
    this.createRandomResults()
    console.log(this.results)
  },
  methods: {
    createRandomResults() {
      const ranLength = this.getRandomIntBetween(4, 10)
      console.log(ranLength)
      for (let index = 0; index < ranLength; index++) {
        this.createRXDataObject()
      }
    },
    createIssueDate() {},
    createRxType() {},
    createStatus() {
      return this.statusOptions[this.getRandomInt(this.statusOptions.length)]
    },
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
    createRXDataObject() {
      const rxObject = {
        rxId: this.createRandomPrescriptionID(),
        status: this.createStatus(),
      }
      this.results.push(rxObject)
    },
    getRandomIntBetween(min: number, max: number) {
      return Math.random() * (max - min) + min
    },
    getRandomInt(max: number) {
      return Math.floor(Math.random() * max)
    },
    copy(rxId: string) {
      this.$refs.(rxId).focus();
      document.execCommand('copy');
    }
  },
})
</script>

<style scoped>
.button-grey {
  background: #dddddd;
  border: none;
  font-weight: 600;
  padding: 4px 10px;
  margin-left: 15px;
  text-transform: uppercase;
}

.button-grey:hover {
  background: rgb(150, 202, 156);
}
</style>
