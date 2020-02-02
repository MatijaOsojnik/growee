<template>
    <v-col class="text-center">

  <v-card width="400px" class="mx-auto my-12" flat color="transparent">
    <img  :src="img" height="90px" />
    <h3 :title="title" class="align-md-center headline" style="margin:1rem 0 0;">{{title}}</h3>
    <v-card-text :text="text">{{text}}</v-card-text>
  </v-card>
    </v-col>
</template>

<script>
export default {
    props: {
        img: String,
        title: String,
        text: String,
    }
};
</script>

<style>
</style>