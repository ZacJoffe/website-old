<template>
  <div class="projects">
    <v-container grid-list-md>
      <v-layout row wrap>
        <v-flex justify-center>
          <v-card>
            <v-card-title primary-title class="headline">Personal Projects</v-card-title>
            <v-card-text>
              A collection of personal projects that I've worked on over the last year or so, and some background information behind them.
            </v-card-text>
          </v-card>
        </v-flex>
      </v-layout>

      <v-layout row wrap>
        <v-flex justify-center>
          <v-card>
            <v-card-title primary-title class="headline"><a href="https://github.com/ZacJoffe/screenshot">Screenshot App</a></v-card-title>
            <v-card-text>
              This is mainly a command line app written in Golang to automate screenshot taking and sharing for my Linux system. Inspired by <a href="https://github.com/ShareX/ShareX">ShareX</a>, an app I used to love back when I used Windows, this app takes screenshots of screen region and copies it to the clipboard. With a flag, you can instead upload the screenshot to <a href="https://imgur.com/">Imgur</a>. 

              To do this, I wrote a library to consume Imgur's REST API, as well as reverse engineering the request to use <a href="https://quad.pe/">quad.pe</a>, a lightweight alternative to Imgur. I also wrote libraries to use <a href="https://gfycat.com/">Gfycat</a> for uploading gifs.

              To get the clipboard working, I wrote wrapper libraries for both xclip and xsel.

              And, lastly, the app was written using <a href="https://github.com/spf13/cobra">Cobra</a>, the same framework used to write the CLI for Docker and Kubernetes.

              I've binded keys to the command via my hotkey manager, so I don't even need a terminal to use it! It was designed specifically for that task and does everything I need it to do.
            </v-card-text>
          </v-card>
        </v-flex>

        <v-flex justify-center>
          <v-card>
            <v-card-title primary-title class="headline">Website</v-card-title>
            <v-card-text>
              This very website was also a project of mine! Written completely from scratch using Vue.js and Vuetify, I tried to create a simple, intuitive layout that looks good on both desktop and mobile. I've always loved material design and Vuetify is a pleasure to develop with.
            </v-card-text>
          </v-card>
        </v-flex>

        <v-flex justify-center>
          <v-card>
            <v-card-title primary-title class="headline">Linux Configuration</v-card-title>
            <v-card-text>
              Over the last year or so, I've been working on tweaking my Arch Linux install to be perfect for my workflow. It's an ongoing process as my workflow changes over time, and there's never the <i>perfect</i> setup, but I feel as if I've gotten pretty close. I've written many shell scripts and custom configuration files for it.
            </v-card-text>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>
