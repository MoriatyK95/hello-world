<script lang="ts">
	let formState = $state({
		name: '',
		birthday: '',
		step: 0,
		error: ' ',
	});

	const QUESTIONS = [
		{
			question: 'What is your name',
			id: 'name',
			type: 'text'
		}
	]

</script>

<main>
	<p>Step: {formState.step + 1}</p>

	{@render formStep({ question: 'What is your name?', id: 'name', type: 'text' })}

	{#if formState.error}
		<p class="error">{formState.error}</p>
	{/if}
</main>

{#snippet formStep({ question, id, type }: { type: string; id: keyof typeof formState; question: string })}
	<article>
		<div>
			<label for={id}>{question}</label>
			<input {type} {id} bind:value={formState[id]} />
		</div>
	</article>
{/snippet}
