<script lang="ts">
	import { Button, Link } from 'carbon-components-svelte';
	import { Launch, TrashCan, Upload } from 'carbon-icons-svelte';

	export let title: string;
	export let viewAllLink: string | undefined;
	export let editLink: string | undefined;
	export let deleteLink: string | undefined;
	export let onSubmit: (() => void) | undefined;
</script>

<div class="w-full flex justify-between items-center mb-3">
	<h2 class="text-xl">{title}</h2>
	<div class="flex items-center gap-3">
		{#if onSubmit}
			<Button icon={Upload} on:click={onSubmit}>Submit</Button>
		{/if}
		{#if editLink}
			<Link icon={Launch} href={editLink}>Edit</Link>
		{/if}
		{#if deleteLink}
			<Link icon={TrashCan} href={deleteLink}>Delete</Link>
		{/if}
		{#if viewAllLink}
			<Link icon={Launch} href={viewAllLink}>View all</Link>
		{/if}
	</div>
</div>
