<template>
  <div class="home">
    <v-container grid-list-md>
      <v-layout row wrap>
        <v-flex justify-center>
          <v-card>
            <div v-if="isMobile">
              <v-img :maxHeight="maxHeight" :src="require('../assets/photo_cropped.jpg')"/>
            </div>
            <div v-else>
              <v-img :maxHeight="maxHeight" :src="require('../assets/photo_very_cropped.jpg')"/>
            </div>
            <v-card-title primary-title>
              <div>
                <div class="headline">Zac Joffe</div>
                <span class="grey--text">Software Engineering - University of Waterloo</span>
              </div>
            </v-card-title>
            <v-card-text>
              I'm a University of Waterloo Software Engineering student with a passion for programming, computers, and engineering.
            </v-card-text>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>

export default {
  props: {
    isMobile: Boolean
  },
  computed: {
    maxHeight() {
      return this.isMobile ? screen.height : screen.height / 1.5
    }
  }
}
</script>
