<template>
  <div class="about">
    <v-container grid-list-md>
      <v-layout row wrap>
        <v-flex justify-center>
          <v-card>
            <v-card-title primary-title class="headline">A Little Bit About Me</v-card-title>
            <v-card-text>
              I'm a second year Software Engineering student at the University of Waterloo in the class of 2023. I am very passionate about software development, and really anything that has to do with computing.
            </v-card-text>
            <v-card-text>
              Ever since I was a kid I was always invested in technology. It started off with my first console: the Nintendo GameCube, where I'd play Super Monkey Ball 2 for hours with my brother trying to finish master mode.

              As I got older, I continued getting into video games, which eventually lead me to building my first computer. And ever since then, I've been continually researching about hardware and love keeping up to date about new technological advancements.
            </v-card-text>
            <v-card-text>
              I got hooked on programming when I started tinkering with Linux in high school. Now I do it for a living, and I couldn't be happier!

              Naturally, I code as a hobby outside of work. Usually I work on stuff that I find useful for my own workflow, such as automation scripts or CLI apps. I love to contribute to open source projects too, specifically those with Linux in mind.

              For more info about my projects, visit the <router-link to="/projects">Projects</router-link> section of the site.
            </v-card-text>
          </v-card>
        </v-flex>
      </v-layout>

      <v-layout row wrap>
        <v-flex justify-center>
          <v-card>
            <v-card-title primary-title class="headline">Programming Prospects</v-card-title>
            <v-card-text>
              Currently, I'm working as a Full Stack Developer at Emailtopia. I love exposing myself to other branches of software development on my own time. For future projects, I want to learn SDL2 and make some games in C++, and maybe try out the SDL bindings for Golang. I'm also very interested in making an NES emulator.
              
              As for languages, I'm very interested in learning Rust.

              I'd love to further contribute to open source projects that I often use and am passionate about (projects like Visual Studio Code, DXVK, Alacritty, QMK, etc).
            </v-card-text>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>
