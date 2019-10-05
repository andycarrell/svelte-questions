
<script>
	import Sandbox from "./Sandbox.svelte";
</script>

<style>
	.page-title {
		text-align: center;
	}

	.text-label {
		margin: 4px 0px;
		font-size: smaller;
	}

	.text-code-sample {
		font-family: monospace;
		padding: 8px;
		border: 1px solid darkgray;
		background-color: lightgray;
		color: gray;
		display: inline-block;
	}

	ul {
		list-style-type: disc;
	}

	code {
		line-height: 0;
		font-size: larger;
	}
</style>

<h1 class="page-title">Svelte questions</h1>

<ul>
	<li>
		<h3>Why declare <code>export const</code>?</h3>
		<div class="text-label">Sample code</div>
		<div class="text-code-sample">
			&lt;script&gt;
			<br />
			&nbsp;&nbsp;export const someVariable = "a value"
			<br />
			&lt;/script&gt;
		</div>
		<p>How is it accessed outside of the component?</p>
	</li>
	<li>
		<h3>Why is <code>:$</code> required for a derived variable, but not variables referenced in functions?</h3>
		<div class="text-label">Sample code</div>
		<div class="text-code-sample">
			let count = 0
			<div>{"function increment() { count += 1 }"}</div>
			$: double = count * 2
		</div>
		<p>Function will always reference latest value of count, double requires <code>:$</code></p>
	</li>
	<li>
		<h3>Why does setting a variable cause a DOM update, but not for derived variables?</h3>
		<div class="text-label">Sample code</div>
		<div class="text-code-sample">
			let count = 0
			<br />
			let double = count * 2 // won't work
			<br />
			$: double = count * 2
		</div>
		<p>Why is this (implementation) difference visible to the user?</p>
	</li>
	<li>
		<h3>Why don't components forward (custom) events by default?</h3>
		<p>Does this apply to all events, or just custom events?</p>
		<p><i>Still a more concise API than the prop drilling generally required to access a message from a child.</i></p>
	</li>
	<li>
		<h3>Why is it recommended to use component bindings sparingly?</h3>
		<p>Is prop drilling preferred - is the recommendation <strong>not</strong> to have multiple sources update a single state.</p>
	</li>
	<li>
		<h3>Why wrap <code>on:click</code> handlers in quotations?</h3>
		<div class="text-label">Sample code</div>
		<div class="text-code-sample">
			let count = 0
			<br />
			&lt;button {`on:click="{() => { count += 1 })}"`}&gt;Like this?&lt;/button&gt;
			<br />
			&lt;button {`on:click={() => { count += 1 })}`}&gt;Or like this&lt;/button&gt;
		</div>
	</li>
	<li>
		<h3>Why the many ways to update a store?</h3>
		<div class="text-label">Sample code</div>
		<div class="text-code-sample">
			// binding to a store
			<br />
			&lt;button {`on:click={() => $count += 1)}`}&gt;Like this?&lt;/button&gt;
			<br />
			&lt;button {`on:click={() => count.set($count + 1))}`}&gt;Or this&lt;/button&gt;
			<br />
			&lt;button {`on:click={() => count.update(c => c + 1))}`}&gt;Or even this&lt;/button&gt;
		</div>
		<p>From the docs: <i>The $name += '!' assignment is equivalent to name.set($name + '!').</i></p>
	</li>
</ul>
