
<script>
	import DecrementButton from "./Decrement.svelte";
	import NumberInput from "./NumberInput.svelte";

	export let count = 0;
	let step = 1;

	$: double = 2 * count;

	function increment() {
		count = count + step;
	}

	function decrement() {
		count = count - step;
	}
</script>

<style>
	p {
		color: purple;
	}
</style>

<p>Count is {count} & doubled is {double}</p>

<NumberInput bind:value={step} />

<br />

<button on:click="{increment}">Increment</button>

<DecrementButton onClick={decrement} />

<DecrementButton variant="danger" onClick={decrement}>
	Another decrement
</DecrementButton>