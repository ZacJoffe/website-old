<template>
  <div class="resume">
    <v-container grid-list-md>
      <v-layout row wrap>
        <v-flex justify-center>
          <v-card>
            <pdf :src="resumeLink"></pdf>
            <v-card-text>
              <v-btn block round @click="downloadResume">Download</v-btn>
            </v-card-text>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
import pdf from 'vue-pdf'
import axios from 'axios'

export default {
  components: {
    pdf
  },
  data() {
    return {
      resumeLink: "https://cors-anywhere.herokuapp.com/https://nbviewer.jupyter.org/github/ZacJoffe/latex-resume/blob/master/resume/zac_joffe_resume.pdf" // fix for prod
    }
  },
  methods: {
    downloadResume() {
      axios({
        url: this.resumeLink,
        method: 'GET',
        responseType: 'blob',
      }).then((response) => {
        const url = window.URL.createObjectURL(new Blob([response.data]));
        const link = document.createElement('a');
        link.href = url;
        link.setAttribute('download', 'zac-joffe-resume.pdf');
        document.body.appendChild(link);
        link.click();
      })
    }
  }
}
</script>
