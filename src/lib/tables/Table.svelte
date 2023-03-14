<script lang="ts">
	import { DataTable, Link } from 'carbon-components-svelte';
	import { Launch, Edit, TrashCan } from 'carbon-icons-svelte';

	export let list: any;
	export let columns: any;
	export let actions: any;
</script>

<DataTable headers={columns} rows={list}>
	<svelte:fragment slot="cell-header" let:header>
		{#if header.key === 'actions'}
			<div class="flex justify-end">{header.value}</div>
		{:else}
			{header.value}
		{/if}
	</svelte:fragment>
	<svelte:fragment slot="cell" let:row let:cell>
		{#if cell.key === 'actions'}
			<div class="flex items-center justify-end gap-6">
				<Link icon={Launch} href={actions.view(row.id)}>View</Link>
				<Link icon={Edit} href={actions.edit(row.id)}>Edit</Link>
				<Link icon={TrashCan} href={actions.delete(row.id)}>Delete</Link>
			</div>
		{:else}
			{cell.value}
		{/if}
	</svelte:fragment>
</DataTable>
