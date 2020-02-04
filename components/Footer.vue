  
<template>
  
  <v-footer
    dark
    padless
    color="#617BE3"
  >
      <v-card
        flat
        tile
        width="100%"
        class="lighten-1 text-center"
            color="#617BE3"
      >
        <v-card-text>
          <v-btn
            v-for="icon in icons"
            :key="icon"
            class="mx-4"
            icon
            :href="icon.link"
          >
            <v-icon size="24px" >{{ icon.name }}</v-icon>
          </v-btn>
        </v-card-text>

        <v-divider></v-divider>

        <v-card-text class="white--text">
          {{ new Date().getFullYear() }} — <strong>Growee</strong>
        </v-card-text>
      </v-card>
  </v-footer>

</template>

<script>
  export default {
    data: () => ({
      icons: [
        {name: 'mdi-github-circle', link: 'https://github.com/SnorkiV3'},
        {name: 'mdi-linkedin', link: 'https://www.linkedin.com/in/matija-osojnik-6b0900193/'},
        {name: 'mdi-facebook', link: 'https://www.facebook.com/matijaosojnik2'},
      ],
    }),
  }
</script>