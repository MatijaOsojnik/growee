<template>
  <div id="app">
    <v-app id="inspire">
            <v-btn icon to="/" style="margin: 2rem 0 0 2rem;"><v-icon size="40px">mdi-arrow-left</v-icon></v-btn>

      <v-content>
        <v-container fluid fill-height>
          <v-layout align-center justify-center>
            <v-flex col10 sm8 md5 lg3>
              <v-card class="elevation-12">
                <v-toolbar color="primary" dark flat>
                  <v-toolbar-title>Login</v-toolbar-title>
                  <v-spacer></v-spacer>
                </v-toolbar>
                <v-card-text>
                  <v-form>
                    <v-text-field label="E-mail" name="login" type="text"></v-text-field>

                    <v-text-field id="password" label="Password" name="password" type="password"></v-text-field>
                    <v-card-actions>
                      <v-btn to="/register">Register</v-btn>
                      <v-spacer></v-spacer>
                      <v-btn color="primary">Login</v-btn>
                    </v-card-actions>
                  </v-form>
                </v-card-text>
              </v-card>
            </v-flex>
          </v-layout>
        </v-container>
      </v-content>
          <svg
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 1440 320"
      preserveAspectRatio="none"
      style="width:100%;height:14rem;display:block;margin-top: -12rem"
    >
      <path
        fill="#617be3"
        fill-opacity="1"
        d="M0,256L48,250.7C96,245,192,235,288,213.3C384,192,480,160,576,165.3C672,171,768,213,864,208C960,203,1056,149,1152,144C1248,139,1344,181,1392,202.7L1440,224L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"
      />
    </svg>
      <Footer></Footer>
    </v-app>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import Footer from "@/components/Footer.vue";
export default {
    components: {
        Footer
    },
  data: () => ({
    drawer: null
  })
};
</script>

<style>
</style>