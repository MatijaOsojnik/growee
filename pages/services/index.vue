<template>
<v-app style="background-color: #f9f7f7">
    <Navbar></Navbar>
  <v-layout
    column
    justify-center
    align-center
  >
    <v-flex
      xs12
      sm8
      md6
    > 
      <v-card>
        <v-card-title>Card Header</v-card-title>
      </v-card>
    </v-flex>
  </v-layout>
</v-app>
</template>

<script>

import Navbar from "@/components/Navbar.vue"
export default {
  components: {
    Navbar
  }
}
</script>