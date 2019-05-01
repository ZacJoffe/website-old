<template>
  <div class="resume">
    <pdf src="https://docs.google.com/viewer?url=raw.github.com/ZacJoffe/latex-resume/master/resume/zac_joffe_resume.pdf" page="1"></pdf>
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
      //link: "https://render.githubusercontent.com/view/pdf?commit=2e0922d3f135cdb3907da7ba4ff9ac32b240ecbc&enc_url=68747470733a2f2f7261772e67697468756275736572636f6e74656e742e636f6d2f5a61634a6f6666652f6c617465782d726573756d652f326530393232643366313335636462333930376461376261346666396163333262323430656362632f726573756d652f7a61635f6a6f6666655f726573756d652e706466&nwo=ZacJoffe%2Flatex-resume&path=resume%2Fzac_joffe_resume.pdf&repository_id=147263961&repository_type=Repository#f0f2a7d7-67f1-4963-8cf2-5c8440896c13"
      link: "https://docs.google.com/viewer?url=raw.github.com/ZacJoffe/latex-resume/master/resume/zac_joffe_resume.pdf"
    }
  }
}
</script>
