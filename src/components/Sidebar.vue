<template>
	<v-navigation-drawer v-model="enabled">
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
</template>

<script>
export default {
  data() {
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
		};
	},
	props: {
		enabled: Boolean
	}
};
</script>

<style>
</style>
