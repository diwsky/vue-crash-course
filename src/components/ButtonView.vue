<template>
	<button
		@click="this.$emit('on-click')"
		class="btn"
		:style="{ background: color }"
	>
		{{ text }}
	</button>
</template>

<script>
export default {
	name: "ButtonView",
	props: {
		text: String,
		color: String,
	},
}
</script>
