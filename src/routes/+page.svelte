<script lang="ts">
	import Header from './Header.svelte';
	let formState = $state({
		name: '',
		birthday: '',
		step: 0,
		error: ' '
	})

</script>

<main>
	<p>Step: {formState.step}</p>
	{#if formState.error} 
		<p class="error">{formState.error}</p> 
	{/if}



	{#if formState.step === 0}
		<div>
			<label for="name"> Your Name </label>
			<input type="text" id="name" bind:value={formState.name}>

		</div>

		<button onclick={ 
			() => {
				if(formState.name != ''){
					formState.step += 1;
					formState.error ='';
				}else{
					formState.error = 'Ur name is empty. Please write your name';
				}
			}
		}> Next </button>

	{/if}
</main>

<style>



	.error {
		color: red;
	}
</style>

