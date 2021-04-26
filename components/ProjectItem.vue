<template>
  <v-card color="rgba(0, 0, 0, 0.6)" dark style="margin: 10px;">

    <v-row>
      <v-col cols="2">
        <v-avatar size="120" style="margin-left: 10px">
          <v-img :src="img_src"></v-img>
        </v-avatar>
      </v-col>
      <v-col>
        <h1 class="item-job-description">{{title}} ({{date}})</h1>
        <p style="white-space: pre-wrap;">{{'\n' + description}}</p>
        <v-chip
          v-for="k in keywordList"
          v-bind:key="k"
          class="ma-2"
          color="primary"
        >{{k}}
        </v-chip>
      </v-col>
    </v-row>

    <v-card-actions>
      <v-btn color="white" v-if="project_link" :href="project_link" target="_blank" outlined>
        <v-icon>mdi-eye</v-icon>
        <v-label>Project</v-label>
      </v-btn>
      <v-btn color="white" v-if="report_link" :href="report_link" target="_blank" outlined>
        <v-icon>mdi-file</v-icon>
        <v-label>Report</v-label>
      </v-btn>

      <v-btn color="white" v-if="source_link" :href="source_link" target="_blank" outlined>
        <v-icon>mdi-code-tags</v-icon>
        <v-label>Source code</v-label>
      </v-btn>

      <v-btn color="white" v-if="description_link" :href="description_link" target="_blank" outlined>
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
      description_link: String,
      keywords: String,
      color: String,
      img_src: String,
      title: String,
      description: String,
      date: String,
      project_link:String,
      report_link: String
    },

    computed: {
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


