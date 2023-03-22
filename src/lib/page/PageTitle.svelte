<script lang="ts">
	import { Link } from 'carbon-components-svelte';
	import { Launch } from 'carbon-icons-svelte';

	export let title: string;
	export let viewAllLink: string;
</script>

<div class="w-full flex justify-between items-center mb-3">
	<h2 class="text-xl">{title}</h2>
	{#if viewAllLink}
		<Link icon={Launch} href={viewAllLink}>View all</Link>
	{/if}
</div>
