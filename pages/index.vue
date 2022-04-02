<template>
  <div class="d-flex justify-space-around">
    <div class="d-flex mt-16">
      <v-row dense>
        <v-col cols="4" md="2">
          <v-card height="100%">
            <v-card-text class="text-center" height="100%">
              <v-icon x-large>mdi-bank</v-icon><br>
              <span>Balance</span>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="4" md="2">
          <v-card height="100%">
            <v-card-text class="text-center ma-0">
              <v-icon x-large>mdi-cash</v-icon><br>
              <span>CashFlow</span>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="4" md="2">
          <v-card height="100%">
            <v-card-text class="text-center">
              <v-icon x-large>mdi-calendar-month</v-icon>
              <div>
                <span>Plan</span>
              </div>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="4" md="2">
          <v-card height="100%">
            <v-card-text class="text-center">
              <v-icon large>mdi-lock</v-icon>
              <div>
                <span>Income</span>
                <span>Protection</span>
              </div>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="4" md="2">
          <v-card height="100%">
            <v-card-text class="text-center">
              <v-icon x-large>mdi-heart-plus</v-icon>
              <div>
                <span>Health Care</span>
              </div>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="4" md="2">
          <v-card height="100%">
            <v-card-text class="d-flex flex-column">
              <div class="ml-5">
                <v-img
                  height="40"
                  width="40"
                  src="/icon/icon-graduate-cap.png"
                />
              </div>
<!--              <v-icon x-large>mdi-heart-plus</v-icon>-->
              <div class="ml-2">
                <span>Education</span>
              </div>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="4" md="2">
          <v-card height="100%">
            <v-card-text class="text-center d-flex flex-column">
              <v-icon x-large>mdi-airplane</v-icon>
              <span>Retirement</span>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="4" md="2">
          <v-card height="100%">
            <v-card-text class="text-center">
              <v-icon x-large>mdi-layers-triple</v-icon>
              <div>
                <span>Other</span>
              </div>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="4" md="2">
          <v-card height="100%">
            <v-card-text class="text-center">
              <v-icon x-large>mdi-monitor</v-icon>
              <div>
                <span>Report</span>
              </div>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>

<style lang="scss">

.main{
  height: 88vh;
}
</style>
