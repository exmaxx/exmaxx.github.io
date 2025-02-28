<script lang="ts">
	import i18n from '$lib/i18n.svelte'
	import SourceCodeNote from './SourceCodeNote.svelte'
	import PrintNote from './PrintNote.svelte'

	const { children } = $props()

	const t = i18n({
		cs: {
			language: 'CZ',
		},
		en: {
			language: 'EN',
		},
	})
</script>

<svelte:head>
	<title>Marek Ulicny - CV ({t('language')})</title>
</svelte:head>

<div
	class="a4:grid-areas-main a4:grid a4:grid-cols-[1fr_auto_1fr] a4:grid-rows-[1fr_auto_1fr] min-h-dvh
	  items-center bg-zinc-400 py-1
	  print:bg-inherit"
>
	<div
		class="text-accent zoom-2 a4:zoom-[3]
			a4:block a4:[grid-area:top] hidden
	  	2xl:justify-self-end 2xl:[grid-area:left] print:hidden"
	>
		<PrintNote />
	</div>

	<div
		class="a4-bottom shadow-2x a4:w-[210mm] a4:max-w-[210mm] relative
		 mx-auto bg-white [grid-area:main]
		  print:pb-0 print:shadow-none"
	>
		{@render children()}

		<SourceCodeNote />
	</div>
</div>
