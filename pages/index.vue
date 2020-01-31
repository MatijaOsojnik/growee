<template>
  <v-app style="background-color: #f9f7f7" light>
    <Navbar></Navbar>
    <v-divider class="mx-4"></v-divider>
    <v-container fluid>
      <v-container>
        <!-- HEADER -->

        <v-row>
          <v-col md="7" lg="5" sm="12" cols="12">
            <v-layout column justify-center align-center>
              <v-flex>
                <h2 class="heading">
                  Best
                  <span class="heading" style="color:#6c63ff">Market Analytics</span> AI Ever.
                </h2>
                <h5
                  class="subheading"
                  style="padding-bottom: 2rem;"
                >Let us get your business ahead of your competition in no-time with the help of marketing automation.</h5>
                <v-form :lazy-validation="lazy" ref="form">
                  <v-row>
                    <v-col md="7">
                      <v-text-field
                        label="Your Business Name"
                        v-model="businessName"
                        outlined
                        rounded
                      />
                    </v-col>
                    <v-col class="text-sm-left text-md-left" md="5">
                      <v-btn height="55px" color="#6c63ff" class="white--text" to="/pricing">
                        <span style="font-size: 15px; padding-right: 5px;">Analyze Market</span>
                      </v-btn>
                    </v-col>
                  </v-row>
                </v-form>
              </v-flex>
            </v-layout>
          </v-col>
          <v-col md="5" lg="7" sm="12" cols="12">
            <img src="~/assets/data-image.svg" height="70%" width="100%" />
          </v-col>
        </v-row>
      </v-container>
    </v-container>

    <!-- BODY -->

    <v-container>
      <v-container fluid>
        <v-layout row justify-space-around>
          <v-row>
            <v-col class="text-center">
              <v-card width="250px" flat color="transparent">
                <img src="~/assets/location.svg" height="80px" />
              </v-card>
            </v-col>
            <v-col>
              <v-card class="text-center" width="250px" flat color="transparent">
                <img src="~/assets/marketing-strategy.svg" height="80px" />
              </v-card>
            </v-col>
            <v-col>
              <v-card class="text-center" width="250px" flat color="transparent">
                <img src="~/assets/web-management.svg" height="80px" />
              </v-card>
            </v-col>
          </v-row>
        </v-layout>
      </v-container>
    </v-container>
  </v-app>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
export default {
  components: {
    Navbar
  },
  data: () => ({
    lazy: true
  }),
  props: {
    businessName: ""
  }
};
</script>

<style>
.cta-lower {
  color: #bbbbbb;
  font-size: 12px;
  padding-right: 5px;
  text-transform: none;
}
.heading {
  padding: 6rem 0 2rem;
  font-size: 42px;
  font-weight: 800;
  color: #1b262c;
}
.subheading {
  padding-bottom: 2rem;
  font-size: 19px;
  font-weight: 700;
  color: #6c7b95;
}
</style>
