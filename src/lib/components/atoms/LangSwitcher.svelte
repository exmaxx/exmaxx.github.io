<script lang="ts">
	import type { Lang } from '$lib/langs'

	interface Props {
		langs: Lang[]
		current: Lang
	}

	const { langs, current }: Props = $props()
</script>

{#each langs as lang}
	{#if lang === current}
		<span class="font-bold">{lang}</span>
	{:else}
		<a href="/{lang}" class="no-underline">{lang}</a>
	{/if}
{/each}
