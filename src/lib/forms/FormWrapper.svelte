<script lang="ts">
	import { Form } from 'carbon-components-svelte';

	export let onSubmit: () => void;
</script>

<Form
	on:submit={(e) => {
		e.preventDefault();
		onSubmit();
	}}
	class="flex items-center gap-3"
>
	<slot />
</Form>
