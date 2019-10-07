<template>
  <v-card color="theme3" dark style="margin: 10px; color: black">

    <v-row>
      <v-col cols="2">
        <v-avatar size="120" style="margin-left: 10px">
          <v-img :src="img_src"></v-img>
        </v-avatar>
      </v-col>
      <v-col>
        <h1 class="item-job-description">{{title}}</h1>
        <h2 class="item-company"><a :href="link" target="_blank">{{company}}</a> {{' -- ' + location + ' -- (' + date + ')'}}</h2>
        <p style="white-space: pre-wrap;">{{description}}</p>
      </v-col>
    </v-row>

  </v-card>
</template>

<script>
    export default {
        props: {
            link: String,
            color: String,
            img_src: String,
            title: String,
            company: String,
            description: String,
            date: String,
            location: String
        }
    };
</script>

<style scoped>

  .item-company {
    margin-top: 10px;
    font-size: medium;
  }
</style>

