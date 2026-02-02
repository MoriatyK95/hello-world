<script lang="ts">
	import Header from './Header.svelte';
	//set state with default value kai
	let name = $state('kai');

	let status: 'OPEN' | 'CLOSED' = $state('OPEN');

    let full_name = $derived( name + " " + "zeng")
</script>

<Header {name} />
<h2>{full_name}</h2>

<input type="text" bind:value={name} />
<p>The store is now {status}</p>
<button
	onclick={() => {
		status = status === 'OPEN' ? 'CLOSED' : 'OPEN';
	}}>Toggle Status</button
>

<style>
</style>
