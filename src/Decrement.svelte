<script>
	export let onClick;
	export let variant = "primary"

	const classMap = {
		primary: "",
		warning: "warning",
		danger: "danger",
	};
</script>

<style>
	button {
		color: blueviolet;
	}

	.warning {
		color: orangered;
	}

	.danger {
		color: red
	}
</style>

<button on:click={onClick} class={classMap[variant]}>
	<slot>decrement</slot>
</button>