<template>
  <v-card color="theme3" dark style="margin: 10px; color: black">

    <v-row>
      <v-col cols="2">
        <v-avatar size="120" style="margin-left: 10px">
          <v-img :src="img_src" ></v-img>
        </v-avatar>
      </v-col>
      <v-col>
        <h1 class="item-job-description">{{title}}</h1>
        <p style="white-space: pre-wrap;">{{'\n' + description}}</p>
        <v-chip
          v-for="k in keywordList"
          class="ma-2"
          color="primary"
        >{{k}}</v-chip>
      </v-col>
    </v-row>

    <v-card-actions>
      <v-btn color="theme2" v-if="source_link" :href="source_link" target="_blank" outlined>
        <v-icon>mdi-github-box</v-icon>
        <v-label>Source code</v-label>
      </v-btn>

      <v-btn color="theme2" v-if="description_link" :href="description_link" target="_blank" outlined >
        <v-icon>mdi-link-box-variant</v-icon>
        <v-label>More</v-label>
      </v-btn>

    </v-card-actions>

  </v-card>
</template>

<script>
    export default {
        props: {
            source_link: String,
            description_link : String,
            keywords : String,
            color: String,
            img_src: String,
            title: String,
            description: String,
        },

        computed : {
            keywordList() {
                if (this.keywords) {
                    return this.keywords.split(',')
                }
                return [];
            },


        }
    };
</script>

<style scoped>

  .item-company {
    margin-top: 10px;
    font-size: medium;
  }
</style>


