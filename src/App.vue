<template>
  <v-app>
		<v-navigation-drawer v-model="drawer" app>
			<v-toolbar flat>
				<v-list-tile>
					<v-list-tile-title class="title">
						Navigate
					</v-list-tile-title>
				</v-list-tile>
			</v-toolbar> 
			<v-divider></v-divider>

			<v-list dense class="pt-0">
				<v-list-tile v-for="item in items" :key="item.title">
					<v-list-tile-action>
						<v-icon>{{ item.icon }}</v-icon>
					</v-list-tile-action>

					<v-list-tile-action>
						<v-list-tile-title>{{ item.title }}</v-list-tile-title>
					</v-list-tile-action>
				</v-list-tile>
			</v-list>
		</v-navigation-drawer>

		<v-toolbar dark color="primary" app>
			<v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
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
			items: [
				{
					title: "Home",
					icon: "mdi-home"
				},
				{
					title: "About",
					icon: "mdi-information"
				},
				{
					title: "Projects",
					icon: "mdi-code-braces"
				}
			],
			drawer: false
    }
  },
  methods: {
    toggleDrawer(value) {
      this.drawer = value
    }
  }
}
</script>
