<template>
  <div class="about">
    <v-container grid-list-md>
      <v-layout row wrap>
        <v-flex justify-center>
          <v-card>
            <v-card-title primary-title class="headline">A Little Bit About Me</v-card-title>
            <v-card-text>
              I'm a second-year Software Engineering student at the University of Waterloo in the class of 2023. I am very passionate about software development, and really anything that has to do with computing.
            </v-card-text>
            <v-card-text>
              Ever since I was a kid, I was always invested in technology. It started with my first console: the Nintendo GameCube, where I'd play Super Monkey Ball 2 for hours with my brother trying to finish master mode.

              As I got older, I continued getting into video games, which eventually lead me to build my first computer. And ever since then, I've been continually researching hardware and love keeping up to date about new technological advancements.
            </v-card-text>
            <v-card-text>
              I got hooked on programming when I started tinkering with Linux in high school. Now I do it for a living, and I couldn't be happier!

              Naturally, I code as a hobby outside of work. Usually, I work on stuff that I find useful for my workflows, such as automation scripts or CLI apps. I love to contribute to open source projects too, specifically those with Linux in mind.

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
              Currently, I'm in my 2A term in Software Engineering. I'm looking for a 4-month position for the winter term (January - April).

              For the future, I'd love to focus on contributing to projects I'm passionate about. I'd also like to learn Rust and develop something with it.
            </v-card-text>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>
