<script lang="ts">
	import i18n from '$lib/i18n.svelte'

	const t = i18n({
		cs: {
			here: 'zde',
			source_code: 'Zdrojový kód tohoto CV',
		},
		en: {
			here: 'here',
			source_code: 'Source code of this CV',
		},
	})
</script>

<div
	class="zoom-1 a4:absolute a4:right-0 a4:bottom-0 a4:m-px a4:origin-bottom-left a4:translate-x-full
			a4:-rotate-90 a4:border-none a4:bg-inherit a4:pl-4 border-t bg-amber-50 py-2 text-center text-zinc-400"
>
	{t('source_code')}: <a href="https://github.com/exmaxx/exmaxx.github.io">{t('here')}</a>
	(HTML, CSS, Tailwind 4)
</div>
