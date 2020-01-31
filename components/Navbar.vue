<template>
  <v-container>
    <v-toolbar dense light color="transparent" elevation="0">
      <v-toolbar-title style="font-weight:900; font-size:30px;">
        <nuxt-link to="/" style="text-decoration: none; color: #1b262c;">Growee</nuxt-link>
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-list v-for="(link, index) in links" :key="index" class="hidden-sm-and-down">
        <v-row>
          <v-col>
            <v-list-item>
              <v-btn text nuxt :to="link.url">
               {{link.name}}
              </v-btn>
            </v-list-item>
          </v-col>
        </v-row>
      </v-list>


      <v-menu bottom left class="hidden-sm-and-down">
        <template v-slot:activator="{ on }" class="hidden-sm-and-down">
              <v-btn
                icon
                v-on="on"
                class="hidden-md-and-up"
                align="right"
              >
                <v-icon>mdi-menu</v-icon>
              </v-btn>
            </template>
       <v-list v-for="(link, index) in links" :key="index" >
        <v-row>
          <v-col>
            <v-list-item>
              <v-btn text nuxt :to="link.url">
               {{link.name}}
              </v-btn>
            </v-list-item>
          </v-col>
        </v-row>
      </v-list>
      </v-menu>

      <v-spacer class="hidden-sm-and-down"/>
      <v-btn color="#6c63ff" class="white--text hidden-sm-and-down" rounded>GET STARTED</v-btn>
    </v-toolbar>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    links: [
      { name: "Home page", url: "/" },
      { name: "Pricing", url: "/pricing" },
      { name: "Services", url: "/services" },
      { name: "About us", url: "/about" },
    ],
  }),
    methods: {
    menuItems () {
      return this.menu
    }
  }
};
</script>

<style>


.theme--dark.v-sheet {
  background-color: none;
  border-color: none;
}
.theme--dark.v-list {
  background: none;
  color: black;
}
.theme--light.v-sheet {
  background-color: none;
  border-color: none;
}
.theme--light.v-list {
  background: none;
  color: black;
}
.theme--dark.v-list-item:not(.v-list-item--active):not(.v-list-item--disabled) {
  color: #3e4149 !important;
  font-weight: 500;
}
</style>