<template>
	<div :key="task.id" v-for="task in tasks">
		<TaskItemVue
			@toggle-reminder="$emit('toggle-reminder', task.id)"
			@delete-task="$emit('delete-task', task.id)"
			:task="task"
		/>
	</div>
</template>

<script>
import TaskItemVue from "./TaskItem.vue"

export default {
	name: "TaskList",
	components: {
		TaskItemVue,
	},
	props: {
		tasks: Array,
	},
	emits: ["delete-task", "toggle-reminder"],
}
</script>
