<script>
	import { navigation } from "./navigationStore.js"

	const items = [
		"questions",
		"sandbox",
	];
</script>

<style>
	nav {
		width: 100%;
		text-align: center;
		margin: 8px auto;
	}

	ul {
		list-style: none;
		padding: 0px 12px;
	}

	li {
		display: inline;
	}

	button {
		margin: 0px 4px;
		border: none;
		background-color: transparent;
		cursor: pointer;
		color: gray;
	}

	button.active {
		color: slategray;
	}

	button:hover,:focus {
		color: black;
		text-decoration: underline;
	}
</style>

<nav>
	<ul>
		{#each items as item}
			<li>
				<button
					class="{$navigation === item && "active"}"
					on:click="{() => { $navigation = item }}"
				>
					{item}
				</button>
			</li>
		{/each}
	</ul>
</nav>
