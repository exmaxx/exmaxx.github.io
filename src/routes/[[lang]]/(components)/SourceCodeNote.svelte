<script lang="ts">
	import i18n from '$lib/i18n'

	interface Props {
		class?: string
	}

	const { class: classes }: Props = $props()

	const t = i18n({
		cs: {
			here: 'zde',
			source_code: 'Projděte si zdrojový kód CV',
		},
		en: {
			here: 'here',
			source_code: 'Check CV source code',
		},
	})
</script>

<div
	class={`zoom-1.5 text-accent a4:border-none a4:bg-inherit a4:pl-4
		mx-1 py-2 text-center ${classes}`}
>
	{t('source_code')}: <a href="https://github.com/exmaxx/curriculum-vitae">{t('here')}</a>

	(HTML, CSS, Tailwind 4)
</div>
