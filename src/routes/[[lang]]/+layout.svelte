<script lang="ts">
	import { page } from '$app/state'
	import i18n from '$lib/i18n'
	import { DEFAULT_LANG } from '$lib/constants'
	import SourceCodeNote from './SourceCodeNote.svelte'
	import PrintNote from './PrintNote.svelte'

	const { children } = $props()

	const lang = page.params.lang || DEFAULT_LANG

	const t = i18n({
		cs: {
			surname: 'Uličný',
			language: 'Česky',
		},
		en: {
			surname: 'Ulicny',
			language: 'English',
		},
	})
</script>

<svelte:head>
	<title>Marek {t('surname')} - CV ({t('language')})</title>
</svelte:head>

<div
	class="sm:grid-areas-main min-h-dvh items-center bg-zinc-400 py-1
	  sm:grid sm:grid-cols-[1fr_auto_1fr] sm:grid-rows-[1fr_auto_1fr]
	  print:bg-inherit"
>
	<div
		class="text-accent zoom-2 sm:zoom-[3]
			hidden sm:block sm:[grid-area:top]
	  	2xl:justify-self-end 2xl:[grid-area:left] print:hidden"
	>
		<PrintNote />
	</div>

	<div
		class="a4-bottom shadow-2x relative mx-auto bg-white
		 [grid-area:main] sm:w-[210mm] sm:max-w-[210mm]
		  print:pb-0 print:shadow-none"
	>
		{@render children()}

		<SourceCodeNote />
	</div>
</div>
