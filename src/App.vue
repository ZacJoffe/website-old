<template>
  <v-app dark>
		<v-navigation-drawer :mini-variant="isMini" :clipped="mini" :temporary="temp" width="250" v-model="drawer" app>
			<v-list dense class="pt-0">
				<div v-if="!isMobile">
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
				</div>
				<div v-else>

					<v-list-tile>Navigate</v-list-tile>

				</div>
			</v-list>

			<v-divider></v-divider>

			<v-list dense class="pt-0">
				<v-list-tile v-for="link in links" :key="link.title" router :to="link.route">
					<v-list-tile-action>
						<v-icon>{{ link.icon }}</v-icon>
					</v-list-tile-action>

					<v-list-tile-content v-if="!isMini">
						<v-list-tile-title>{{ link.title }}</v-list-tile-title>
					</v-list-tile-content>
				</v-list-tile>
			</v-list>
		</v-navigation-drawer>

		<v-toolbar :clipped-left="isMini" dark color="primary" app>
			<v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
			<v-toolbar-title class="headline">{{ toolbarTitle }}</v-toolbar-title>
			<v-spacer></v-spacer>

			<v-toolbar-items>
				<v-tooltip bottom>
					<template v-slot:activator="{ on }">
						<v-btn icon href="https://github.com/ZacJoffe" v-on="on">
							<v-icon>mdi-github-circle</v-icon>
						</v-btn>
					</template>
					<span>My GitHub</span>
				</v-tooltip>

				<v-tooltip bottom>
					<template v-slot:activator="{ on }">
						<v-btn icon href="https://www.linkedin.com/in/zacjoffe/" v-on="on">
							<v-icon>mdi-linkedin</v-icon>
						</v-btn>
					</template>
					<span>My LinkedIn</span>
				</v-tooltip>
			</v-toolbar-items>
		</v-toolbar>

		<v-content>
			<transition name="fade">
				<router-view :isMobile="isMobile"></router-view>
			</transition>
		</v-content>
  </v-app>
</template>

<script>
import { isMobile } from 'mobile-device-detect'
export default {
  name: 'App',
  data() {
    return {
			links: [
				{
					title: "Home",
					toolbarTitle: "Zac Joffe",
					icon: "mdi-home",
					route: "/"
				},
				{
					title: "About",
					toolbarTitle: "About Me",
					icon: "mdi-information",
					route: "/about"
				},
				{
					title: "Projects",
					toolbarTitle: "My Projects",
					icon: "mdi-code-braces",
					route: "/projects"
				},
				{
					title: "Resume",
					toolbarTitle: "My Resume",
					icon: "mdi-file-document-box",
					route: "/resume"
				},
				{
					title: "Contact",
					toolbarTitle: "Contact Information",
					icon: "mdi-contacts",
					route: "/contact"
				}
			],
			toolbarTitle: "Zac Joffe",
			isMobile: false,
			isPhone: false,
			drawer: false,
			mini: true,
			temp: false
    }
	},
	beforeDestroy() {
    if (typeof window !== 'undefined') {
      window.removeEventListener('resize', this.onResize, { passive: true })
    }
  },
  mounted() {
		this.isPhone = isMobile
		this.onResize()
		this.setToolbarTitle()
		if (!this.isMobile) {
			this.drawer = true
		}
		window.addEventListener('resize', this.onResize, { passive: true })
	},
	watch: {
		$route() {
			this.setToolbarTitle()
		}
	},
  methods: {
		onResize() {
			//this.isMobile = window.innerWidth < 600
			if (this.isPhone) {
				this.isMobile = true
			} else {
				this.isMobile = window.innerWidth < screen.width / 2
			}
			//this.isMobile = window.innerWidth < screen.width / 2
		},
		setToolbarTitle() {
			var index = this.links.findIndex(link => link.route === this.$route.path)
			this.toolbarTitle = this.links[index].toolbarTitle
		}
	},
	computed: {
		isMini() {
			return (this.mini && !this.isMobile)
		}
	}
}
</script>
