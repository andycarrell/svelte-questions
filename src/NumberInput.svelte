<script>
	export const aThing = "thing"
	export let value = 0;
</script>

<style>
	.danger {
		color: red
	}
</style>

<input
	bind:value
	type=number
	class={value === 0 ? "danger" : ""}
/>