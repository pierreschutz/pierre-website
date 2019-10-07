<template>
  <v-card :color="color" dark>
    <v-list-item three-line>
      <v-list-item-content class="align-self-start">
        <v-list-item-title class="headline mb-2" v-text="title"></v-list-item-title>
        <v-list-item-subtitle :v-text="location + ' bonjoru  ' +  date"></v-list-item-subtitle>
      </v-list-item-content>
    </v-list-item>

    <v-list-item-avatar size="125" tile>
      <v-img :src="img_src"></v-img>
    </v-list-item-avatar>
  </v-card>
</template>

<script>
export default {
  props: {
    color: String,
    img_src: String,
    title: String,
    description: String,
    date: String,
    location: String
  }
};
</script>

