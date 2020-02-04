<template>
  <v-app style="background-color: #f9f7f7">
    <Navbar></Navbar>
    <svg
      xmlns="http://www.w3.org/2000/svg"
      preserveAspectRatio="none"
      style="width:100%;height:14rem;display:block;margin-top: -2rem"
      viewBox="0 0 1440 320"
    >
      <path
        fill="#617be3"
        fill-opacity="1"
        d="M0,96L48,90.7C96,85,192,75,288,74.7C384,75,480,85,576,96C672,107,768,117,864,133.3C960,149,1056,171,1152,170.7C1248,171,1344,149,1392,138.7L1440,128L1440,0L1392,0C1344,0,1248,0,1152,0C1056,0,960,0,864,0C768,0,672,0,576,0C480,0,384,0,288,0C192,0,96,0,48,0L0,0Z"
      />
    </svg>
    <v-layout column justify-center align-center>
      <v-flex xs12 sm8 md6>
        <v-card class="align-content-center mx-auto" max-width="344px" >
          <v-card-title class="headline justify-center">The Business Package</v-card-title>
          <v-card-text>
            <v-list three-line>
              <v-list-item>
                <v-list-item-content>
                  <v-list-item-title>All Market Analytics</v-list-item-title>
                  <v-list-item-subtitle>Set the content filtering level to restrict appts that can be downloaded</v-list-item-subtitle>
                </v-list-item-content>
              </v-list-item>
              <v-list-item>
                <v-list-item-content>
                  <v-list-item-title>Stats</v-list-item-title>
                  <v-list-item-subtitle>Require password for purchase or use password to restrict purchase</v-list-item-subtitle>
                </v-list-item-content>
              </v-list-item>
                            <v-list-item>
                <v-list-item-content>
                  <v-list-item-title>Stats</v-list-item-title>
                  <v-list-item-subtitle>Require password for purchase or use password to restrict purchase</v-list-item-subtitle>
                </v-list-item-content>
              </v-list-item>
            </v-list>
          </v-card-text>
          <v-card-subtitle class="text-center">Contact Us For Price</v-card-subtitle>
        </v-card>
      </v-flex>
    </v-layout>

    <svg
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 1440 320"
      preserveAspectRatio="none"
      style="width:100%;height:14rem;display:block;margin-top: -2rem"
    >
      <path
        fill="#617be3"
        fill-opacity="1"
        d="M0,256L48,250.7C96,245,192,235,288,213.3C384,192,480,160,576,165.3C672,171,768,213,864,208C960,203,1056,149,1152,144C1248,139,1344,181,1392,202.7L1440,224L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"
      />
    </svg>
    <Footer></Footer>
  </v-app>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import Footer from "@/components/Footer.vue";
export default {
  components: {
    Navbar,
    Footer
  }
};
</script>