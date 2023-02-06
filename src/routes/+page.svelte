<script lang="ts">
	import { Paginator } from '@skeletonlabs/skeleton';

	export let data: {limit: number}

	$: page = {
		offset: 0,
		limit: data.limit,
		size: 100,
		amounts: [10, 25, 50, 100]
	};

	const onAmountChange = async (event: CustomEvent) => {
		console.log(event.detail);
    };
</script>

<Paginator bind:settings={page} on:amount={onAmountChange}/>
