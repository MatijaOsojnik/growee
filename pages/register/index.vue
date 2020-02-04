<template>
  <div id="app">
    <v-app id="inspire">
      <v-btn icon to="/" style="margin: 2rem 0 0 2rem;">
        <v-icon size="40px">mdi-arrow-left</v-icon>
      </v-btn>
      <v-container fluid fill-height>
        <v-layout align-center justify-center>
          <v-flex col10 sm8 md5 lg3>
            <v-card class="elevation-12">
              <v-snackbar v-model="snackbar" absolute top right color="success">
                <span>Registration successful!</span>
                <v-icon dark>mdi-checkbox-marked-circle</v-icon>
              </v-snackbar>
              <v-toolbar color="primary" dark flat>
                <v-toolbar-title>Register</v-toolbar-title>
                <v-spacer></v-spacer>
              </v-toolbar>
              <v-card-text>
                <v-form ref="form" @submit.prevent="submit" @keydown.enter.prevent>
                  <v-text-field
                    v-model="form.firstName"
                    :rules="noEmptyRules"
                    label="First Name"
                    required
                  ></v-text-field>

                  <v-text-field
                    v-model="form.lastName"
                    :rules="noEmptyRules"
                    label="Last Name"
                    required
                  ></v-text-field>

                  <v-text-field
                    v-model="form.companyUrl"
                    :rules="noEmptyRules"
                    label="Company Website"
                    required
                  ></v-text-field>

                  <v-text-field v-model="form.email" :rules="emailRules" label="Email" required></v-text-field>

                  <v-text-field
                    v-model="form.password"
                    :rules="[passwordRules.required, passwordRules.min]"
                    label="Password"
                    type="password"
                    hint="At least 8 characters"
                    counter
                    required
                  ></v-text-field>

                  <v-text-field
                    v-model="form.confirmPasword"
                    :rules="[passwordRules.confirm]"
                    label="Confirm Password"
                    type="password"
                    required
                  ></v-text-field>

                  <v-card-actions>
                    <v-btn :to="{name: 'login'}">Login</v-btn>
                    <v-spacer></v-spacer>
                    <v-btn :disabled="!formIsValid" text color="primary" type="submit">Register</v-btn>
                  </v-card-actions>

                  <v-checkbox v-model="form.terms" color="green">
                    <template v-slot:label>
                      <div @click.stop>
                        Do you accept the
                        <a href="javascript:;" @click.stop="terms = true">terms</a>
                        and
                        <a
                          href="javascript:;"
                          @click.stop="conditions = true"
                        >conditions?</a>
                      </div>
                    </template>
                  </v-checkbox>
                </v-form>

                <v-dialog v-model="terms" width="70%">
                  <v-card>
                    <v-card-title class="title">Terms</v-card-title>
                    <v-card-text v-for="n in 5" :key="n">{{ content }}</v-card-text>
                    <v-card-actions>
                      <v-spacer></v-spacer>
                      <v-btn text color="purple" @click="terms = false">Ok</v-btn>
                    </v-card-actions>
                  </v-card>
                </v-dialog>
                <v-dialog v-model="conditions" width="70%">
                  <v-card>
                    <v-card-title class="title">Conditions</v-card-title>
                    <v-card-text v-for="n in 5" :key="n">{{ content }}</v-card-text>
                    <v-card-actions>
                      <v-spacer></v-spacer>
                      <v-btn text color="purple" @click="conditions = false">Ok</v-btn>
                    </v-card-actions>
                  </v-card>
                </v-dialog>
              </v-card-text>
            </v-card>
          </v-flex>
        </v-layout>
      </v-container>
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
    Footer,
    Navbar
  },
  data(vm) {
    const defaultForm = Object.freeze({
      firstName: "",
      lastName: "",
      CompanyUrl: "",
      email: "",
      password: "",
      confirmPassword: "",
      terms: false
    });
    return {
      form: Object.assign({}, defaultForm),
      noEmptyRules: [value => !!value || "Cannot be empty."],
      emailRules: [
        v => !!v || "E-mail is required",
        v => /.+@.+/.test(v) || "E-mail must be valid"
      ],
      passwordRules: {
        required: value => !!value || "Required",
        min: value => value.length >= 8 || "Min 8 characters",
        confirm: value => value === vm.form.password || "Password don't match"
      },
      conditions: false,
      snackbar: false,
      terms: false,
      content: `Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio. Praesent libero. Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum imperdiet. Duis sagittis ipsum. Praesent mauris. Fusce nec tellus sed augue semper porta. Mauris massa. Vestibulum lacinia arcu eget nulla. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Curabitur sodales ligula in libero. Sed dignissim lacinia nunc.`,
      defaultForm
    };
  },

  computed: {
    
    
  },
  methods: {
    formIsValid() {
      return (
        this.form.firstName &&
        this.form.companyUrl &&
        this.form.email &&
        this.form.password &&
        this.form.confirmPassword &&
        this.form.terms
      );
    },
    resetForm() {
      this.form = Object.assign({}, this.defaultForm);
      this.$refs.form.reset();
    },
    submit() {
      this.snackbar = true;
      this.resetForm();
    }
  }
};
</script>