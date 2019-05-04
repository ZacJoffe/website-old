<template>
  <v-app dark>
		<v-navigation-drawer :mini-variant="mini" :clipped="mini" :temporary="temp" width="250" v-model="drawer" app justify-center>
			<v-list dense class="pt-0">
				<v-list-tile v-if="mini" @click.stop="mini = !mini">
					<v-list-tile-action>
						<v-icon>mdi-chevron-right</v-icon>
					</v-list-tile-action>
				</v-list-tile>
				<v-list-tile v-else @click.stop="mini = !mini">
					<v-list-tile-action>
						<v-icon>mdi-chevron-left</v-icon>
					</v-list-tile-action>

					<v-list-tile-content>
						<v-list-tile-title>Minimize</v-list-tile-title>
					</v-list-tile-content>
				</v-list-tile>
			</v-list>
			<!--
			<v-toolbar flat>
				<v-list-tile>
					<v-list-tile-title class="title">
						Navigate
					</v-list-tile-title>
				</v-list-tile>
			</v-toolbar> 
			-->
			<v-divider></v-divider>

			<v-list dense class="pt-0">
				<v-list-tile v-for="link in links" :key="link.title" router :to="link.route">
					<v-list-tile-action>
						<v-icon>{{ link.icon }}</v-icon>
					</v-list-tile-action>

					<v-list-tile-content v-if="!mini">
						<v-list-tile-title>{{ link.title }}</v-list-tile-title>
					</v-list-tile-content>
				</v-list-tile>
			</v-list>
		</v-navigation-drawer>

		<v-toolbar :clipped-left="mini" dark color="primary" app>
			<v-toolbar-side-icon v-if="!mini" @click.stop="drawer = !drawer"></v-toolbar-side-icon>
			<v-toolbar-title class="headline">Zac Joffe</v-toolbar-title>
			<v-spacer></v-spacer>

			<v-toolbar-items>
				<v-btn icon href="https://github.com/ZacJoffe">
					<v-icon>mdi-github-circle</v-icon>
				</v-btn>

				<v-btn icon href="https://www.linkedin.com/in/zacjoffe/">
					<v-icon>mdi-linkedin</v-icon>
				</v-btn>
			</v-toolbar-items>
		</v-toolbar>

		<v-content>
			<!--
			<transition name="router-anim" enter-active-class="animated fadeInDown" leave-active-class="animated fadeInUp">
				-->
			<transition name="fade">
				<router-view></router-view>
			</transition>
		</v-content>
		<!--
    <v-container flex>
      <v-layout>
        <v-flex>
          <Sidebar @toggle-drawer="toggleDrawer" :enabled="drawer"/>
        </v-flex>
        <v-flex>
          <Toolbar />
        </v-flex>
      </v-layout>
    </v-container>


    <Toolbar />
    <Sidebar @toggle-drawer="toggleDrawer" :enabled="drawer"/>
		-->
    <!--
    <v-toolbar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>Vuetify</span>
        <span class="font-weight-light">MATERIAL DESIGN</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        flat
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
      >
        <span class="mr-2">Latest Release</span>
      </v-btn>
    </v-toolbar>

    <v-content>
      <HelloWorld/>
    </v-content>
    -->
  </v-app>
</template>

<script>
//import HelloWorld from './components/HelloWorld'
//import Toolbar from './components/Toolbar'
//import Sidebar from './components/Sidebar'

export default {
  name: 'App',
  components: {
    //HelloWorld
    //Toolbar,
    //Sidebar
  },
  data () {
    return {
			links: [
				{
					title: "Home",
					icon: "mdi-home",
					route: "/"
				},
				{
					title: "About",
					icon: "mdi-information",
					route: "/about"
				},
				{
					title: "Projects",
					icon: "mdi-code-braces",
					route: "/projects"
				},
				{
					title: "Resume",
					icon: "mdi-file-document-box",
					route: "/resume"
				}
			],
			drawer: true,
			mini: true,
			temp: false
    }
  },
  methods: {
    toggleDrawer(value) {
      this.drawer = value
    }
  }
}
</script>
