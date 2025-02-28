<script lang="ts">
	import i18n from '$lib/i18n.svelte'

	const t = i18n({
		cs: {
			surname: 'Uličný',
		},
		en: {
			surname: 'Ulicny',
		},
	})
</script>

<div class="text-center">
	<h1>Marek {t('surname')}</h1>
	<p class="zoom-[1.8] a4:mt-0 my-2 leading-9">Senior Frontend Developer</p>
</div>
