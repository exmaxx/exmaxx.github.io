<script lang="ts">
	import { page } from '$app/state'
	import SourceCodeNote from './SourceCodeNote.svelte'
	import PrintNote from './PrintNote.svelte'

	const { children } = $props()
</script>

<svelte:head>
	<title>Marek Uličný - CV ({page.params.lang || 'en'})</title>
</svelte:head>

<div
	class="sm:grid-areas-main min-h-dvh items-center
	 bg-zinc-400 py-1 sm:grid sm:grid-cols-[1fr_auto_1fr] sm:grid-rows-[1fr_auto_1fr]
	  print:bg-inherit"
>
	<PrintNote />

	<div
		class="a4-bottom shadow-2x relative mx-auto bg-white
		 [grid-area:main] sm:w-[210mm] sm:max-w-[210mm]
		  print:pb-0 print:shadow-none"
	>
		{@render children()}

		<SourceCodeNote />
	</div>
</div>
