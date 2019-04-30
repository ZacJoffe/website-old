<template>
  <div class="home">
    <v-container grid-list-md>
      <v-layout row wrap>
        <v-flex justify-center>
          <v-card>
            <v-img :src="require('../assets/photo.jpg')"/>
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


    <!--
    <v-card>
      <v-card-title primary-title>
        <div>
          <div class="headline">Zac Joffe</div>
          <span class="grey--text">Software Engineering - University of Waterloo</span>
        </div>
      </v-card-title>
    </v-card>
    -->
  </div>
</template>

<script>

export default {
  components: {

  }
}
</script>
