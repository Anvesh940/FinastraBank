<template>
  <div class="home">
    <v-container class="mt-3">
      <h4 class="headline font-weight-bold">
        Savings Account
      </h4>
      <v-row>
        <v-card
          flat
          to="/index"
          v-for="(account, i) in dataFile.savings"
          :key="i"
        >
          <v-col class="mt-3">
            <div class="d-flex mr-16">
              <v-img
                :src="require('../assets/' + account.image)"
                contain
                max-height="100px"
                max-width="170px"
              />
              <v-btn class="mt-16 text-capitalize" :small="true">
                <v-icon class="ml-n2 mr-2" :small="true">
                  mdi-arrow-right-drop-circle
                </v-icon>
                Apply now
              </v-btn>
            </div>
            <p class="mt-2">
              <b>{{ account.type }} Savings</b>
            </p>
            <p class="mt-n3">ROI - {{ account.ROI }}</p>
            <p class="mt-n3">
              Max Transaction/day {{ account.transaction }} GBP
            </p>
          </v-col>
        </v-card>
      </v-row>

      <h4 class="headline font-weight-bold mt-3">
        Fixed Deposits
      </h4>

      <v-row>
        <v-card flat v-for="(account, i) in dataFile.fixeddeposits" :key="i">
          <v-col class="mt-3">
            <div class="d-flex mr-16">
              <v-img
                :src="require('../assets/' + account.image)"
                contain
                max-height="100px"
                max-width="170px"
              />
              <v-btn class="mt-16 text-capitalize" :small="true">
                <v-icon class="ml-n2 mr-2" :small="true">
                  mdi-arrow-right-drop-circle
                </v-icon>
                Apply now
              </v-btn>
            </div>
            <p class="mt-2">
              <b>{{ account.type }} Fixed Deposits</b>
            </p>
            <p class="mt-n3">Term - {{ account.term }} years</p>
            <p class="mt-n3">ROI - {{ account.ROI }}</p>
            <p class="mt-n3">Min-Max amount {{ account.amount }} GBP</p>
          </v-col>
        </v-card>
      </v-row>
    </v-container>
  </div>
</template>

<script>
let data = require("../data.json");
export default {
  name: "Home",
  data: () => ({
    dataFile: {},
  }),
  mounted() {
    this.dataFile = { ...data };
  },
};
</script>

<style scoped>
.v-card {
  text-decoration: none;
}
</style>
