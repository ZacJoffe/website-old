<template>
  <div class="projects">
    <v-container grid-list-md>
      <v-layout row wrap>
        <v-flex justify-center>
          <v-card>
            <v-img :max-height="maxHeight" :src="require('../assets/robot.jpg')"/>
            <v-card-title primary-title>
              <div>
                <div class="headline">Projects</div>
                <span class="grey--text">A collection of (mostly) personal projects that I've worked on.</span>
              </div>
            </v-card-title>
            <!--
            <v-card-title primary-title class="headline">Projects</v-card-title>
            <v-card-text>
              A collection of (mostly) personal projects that I've worked on over the last year or so, and some background information behind them.
            </v-card-text>
            -->
          </v-card>
        </v-flex>
      </v-layout>

      <v-layout row wrap>
        <v-flex justify-center>
          <v-card>
            <v-card-title primary-title>
              <span class="headline">Screenshot App</span>
              <v-flex text-xs-right>
                <v-tooltip bottom>
                  <template v-slot:activator="{ on }">
                    <v-btn icon href="https://github.com/ZacJoffe/screenshot" v-on="on">
                      <v-icon>mdi-git</v-icon>
                    </v-btn>
                  </template>
                  <span>Source Code</span>
                </v-tooltip>
              </v-flex>
            </v-card-title>
            <v-card-text>
              This is mainly a command line app written in Golang to automate taking and sharing screenshots for my Linux system. Inspired by <a href="https://github.com/ShareX/ShareX">ShareX</a>, an app I used to love back when I used Windows, this app takes screenshots of a screen region and copies it to the clipboard. With a flag, you can instead upload the screenshot to Imgur. 

              To do this, I wrote a library to consume Imgur's REST API, as well as reverse engineering the request to use quad.pe, a lightweight alternative to Imgur. I also wrote libraries to use Gfycat for uploading gifs.

              To get the clipboard working, I wrote wrapper libraries for both xclip and xsel.

              And, lastly, the app was written using <a href="https://github.com/spf13/cobra">Cobra</a>, the same framework used to write the CLI for Docker and Kubernetes.

              I've binded keys to run the command via my hotkey manager (which can be found in my dotfiles repository, link to that below), so I don't even need a terminal to use it! It was designed specifically for that task and does everything I need it to do.
            </v-card-text>
          </v-card>
        </v-flex>

        <v-flex justify-center>
          <v-card>
            <v-card-title primary-title>
              <span class="headline">Website</span>
              <v-flex text-xs-right>
                <v-tooltip bottom>
                  <template v-slot:activator="{ on }">
                    <v-btn small icon href="https://github.com/ZacJoffe/website" v-on="on">
                      <v-icon>mdi-git</v-icon>
                    </v-btn>
                  </template>
                  <span>Source Code</span>
                </v-tooltip>
              </v-flex>
            </v-card-title>
            <v-card-text>
              This very website is also a project of mine! Written completely from scratch using Vue.js and Vuetify, I tried to create a simple and intuitive layout that looks good on both desktop and mobile. I've always loved material design and Vuetify is a pleasure to develop with.
            </v-card-text>
          </v-card>
        </v-flex>

        <v-flex justify-center>
          <v-card>
            <v-card-title primary-title>
              <span class="headline">Linux Configuration</span>
              <v-flex text-xs-right>
                <v-tooltip bottom>
                  <template v-slot:activator="{ on }">
                    <v-btn small icon href="https://github.com/ZacJoffe/dotfiles" v-on="on">
                      <v-icon>mdi-git</v-icon>
                    </v-btn>
                  </template>
                  <span>Source Code</span>
                </v-tooltip>
              </v-flex>
            </v-card-title>
            <v-card-text>
              Over the last year or so, I've been working on tweaking my Arch Linux install to be perfect for my workflow. It's an ongoing process as my workflow changes over time, and there's never the <i>perfect</i> setup, but I feel as if I've gotten pretty close. I've written many shell scripts and custom configuration files for it.
            </v-card-text>
          </v-card>
        </v-flex>
      </v-layout>
        <v-flex justify-center>
          <v-card>
            <v-card-title primary-title>
              <span class="headline">Rubik's Cube Solving Robot</span>
              <v-flex text-xs-right>
                <v-tooltip bottom>
                  <template v-slot:activator="{ on }">
                    <v-btn small icon href="https://github.com/ZacJoffe/two-by-two-solver" v-on="on">
                      <v-icon>mdi-git</v-icon>
                    </v-btn>
                  </template>
                  <span>Source Code</span>
                </v-tooltip>
              </v-flex>
            </v-card-title>
            <v-card-text>
              For our final project in my first semester, we had to build a Lego Mindstorm EV3 robot to do something cool. Me and two other people build a robot that solves a 2x2 Rubik's cube.

              We used an open source algorithm to determine the solution of a given scramble, and the robot executed the moves to solve the cube generally in 10 turns or less.
            </v-card-text>
          </v-card>
        </v-flex>
    </v-container>
  </div>
</template>

<script>

export default {
  data() {
    return {

    }
  },
  computed: {
    maxHeight() {
      return screen.height / 3
    }
  }
}
</script>
