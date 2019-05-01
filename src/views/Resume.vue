<template>
  <div class="resume">
    <v-container grid-list-md>
      <v-layout row wrap>
        <v-flex justify-center>
          <v-card>
            <pdf :src="resumeLink"></pdf>
            <v-btn @click="downloadResume">Download</v-btn>
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
      //link: "https://docs.google.com/viewer?url=raw.github.com/ZacJoffe/latex-resume/master/resume/zac_joffe_resume.pdf"
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
