<template>
	<header>
		<h1>{{ title }}</h1>
		<ButtonView
			v-show="homePage"
			@on-click="$emit('on-add-task')"
			:text="showAddTask ? 'Close' : 'Add Task'"
			:color="showAddTask ? 'red' : 'green'"
			showAddTask="{{showAddTask}}"
		/>
	</header>
</template>

<script>
import ButtonView from "./ButtonView"
export default {
	name: "HeaderView",
	props: {
		title: String,
		showAddTask: Boolean,
	},
	components: {
		ButtonView,
	},
	computed: {
		homePage() {
			return this.$route.path === "/"
		},
	},
}
</script>

<style scoped>
header {
	display: flex;
	justify-content: space-between;
	align-items: center;
	margin-bottom: 20px;
}
</style>
