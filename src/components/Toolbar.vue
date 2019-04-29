<template>
  <v-toolbar dark color="primary" clipped-left>
		<v-toolbar-side-icon @click.stop="toggleDrawer"></v-toolbar-side-icon>
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
</template>

<script>
export default {
  data() {
    return {
			drawer: false
		};
  },
	methods: {
		toggleDrawer() {
			this.drawer = !this.drawer
			this.$emit('toggle-drawer', this.drawer)
		}
	}
};
</script>

<style>
</style>
