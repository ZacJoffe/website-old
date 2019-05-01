<template>
  <div class="resume">
    <pdf :src="link"></pdf>
  </div>
</template>

<script>
import pdf from 'pdfvuer'

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
