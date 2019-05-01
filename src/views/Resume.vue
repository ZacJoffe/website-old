<template>
  <div class="resume">
    <v-container grid-list-md>
      <v-layout row wrap>
        <v-flex justify-center>
          <v-card>
            <pdf :src="link"></pdf>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
import pdf from 'vue-pdf'

export default {
  components: {
    pdf
  },
  data() {
    return {
      //link: "https://docs.google.com/viewer?url=raw.github.com/ZacJoffe/latex-resume/master/resume/zac_joffe_resume.pdf"
      link: "https://cors-anywhere.herokuapp.com/https://nbviewer.jupyter.org/github/ZacJoffe/latex-resume/blob/master/resume/zac_joffe_resume.pdf" // fix for prod
    }
  }
}
</script>
