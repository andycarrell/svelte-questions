
<script>
	import Sandbox from "./Sandbox.svelte";
	import Questions from "./Questions.svelte";
	import Navigation from "./Navigation.svelte";
	import { navigation as navigationStore } from "./navigationStore";
</script>

<style>

</style>

<Navigation />

{#if $navigationStore === "questions"}
	<Questions />
{/if}
{#if $navigationStore === "sandbox"}
	<Sandbox />
{/if}

