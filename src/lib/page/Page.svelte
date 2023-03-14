<script lang="ts">
	import { Breadcrumb, BreadcrumbItem, Button, Link } from 'carbon-components-svelte';
	import { Launch, TrashCan, Upload } from 'carbon-icons-svelte';

	export let breadcrumbs: any;
	export let title: any;
	export let onSubmit: any;
	export let fields: any;
	export let actions: any;
</script>

<div class="w-full">
	{#if !!breadcrumbs}
		<Breadcrumb noTrailingSlash>
			{#each breadcrumbs as breadcrumb}
				<BreadcrumbItem href={breadcrumb.link}>{breadcrumb.title}</BreadcrumbItem>
			{/each}
		</Breadcrumb>
	{/if}

	<div class="w-full flex justify-between items-center mb-3">
		<h2 class="text-xl">{title}</h2>
		{#if !!actions}
			<div class="flex items-center gap-3">
				{#if !!onSubmit}
					<Button icon={Upload} on:click={onSubmit}>Submit</Button>
				{/if}
				<Link icon={Launch} href={actions.edit}>Edit</Link>
				<Link icon={TrashCan} href={actions.delete}>Delete</Link>
			</div>
		{/if}
	</div>

	{#if !!fields}
		{#each fields as field}
			<div class="flex items-center gap-4">
				<h3 class="text-lg">{field.title}</h3>
				<p>{field.value}</p>
			</div>
		{/each}
	{/if}

	<!-- <div class="w-full mb-6">
		<div class="w-full flex justify-between items-center mb-3">
			<h2 class="text-xl">Location Templates</h2>
			<Link icon={Launch} href={ROUTES.organizations.organization.locationTemplates.base(data.id)}
				>View all</Link
			>
		</div>
		{#if $locationTemplates}
			<LocationTemplatesTable organizationId={data.id} />
		{/if}
	</div> -->

	<!-- <div class="w-full mb-6">
		<div class="w-full flex justify-between items-center mb-3">
			<h2 class="text-xl">Location Schemas</h2>
			<Link icon={Launch} href={ROUTES.organizations.organization.locationSchemas.base(data.id)}
				>View all</Link
			>
		</div>
		{#if $locationSchemas}
			<LocationSchemasTable organizationId={data.id} />
		{/if}
	</div> -->

	<!-- <div class="w-full mb-6">
		<div class="w-full flex justify-between items-center mb-3">
			<h2 class="text-xl">Managers</h2>
			<Link icon={Launch} href={ROUTES.organizations.organization.managers.base(data.id)}
				>View all</Link
			>
		</div>
		{#if $managers}
			<ManagersTable organizationId={data.id} />
		{/if}
	</div> -->
	<slot />
</div>
