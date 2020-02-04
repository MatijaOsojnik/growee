<template>

            <v-row>

              <v-col
                md="6"
                lg="6"
                sm="12"
                cols="12"
                class="column justify-center justify-space-around"
              >
                <v-layout>
                  <v-flex class="column align-center ma-12">
                    <h1 class="display-1" :title="title">{{title}}</h1>
                    <h5
                      class="description" :text="text"
                    >{{text}}</h5>
                  </v-flex>
                </v-layout>
              </v-col>
                <v-col
                md="6"
                lg="6"
                sm="12"
                cols="12"
                class="text-center column align-content-center align-self-center justify-center"
                >
                <img :src="img" width="80%" alt />
              </v-col>
            </v-row>

</template>

<script>
export default {
    props: {
        img: String,
        title: String,
        text: String,
    }
}
</script>

<style>

</style>