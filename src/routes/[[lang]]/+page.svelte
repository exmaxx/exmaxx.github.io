<script lang="ts">
	import i18n from '$lib/i18n'
	import Title from './(components)/Title.svelte'
	import SkillsHighlight from './(components)/SkillsHighlight.svelte'
	import Experience from './(components)/Experience.svelte'
	import SkillsTech from './(components)/SkillsTech.svelte'
	import Lead from './(components)/Lead.svelte'
	import Contacts from './(components)/Contacts.svelte'
	import LangSwitcher from '$lib/components/organisms/LangSwitcher.svelte'
	import Education from './(components)/Education.svelte'
	import Profiles from './(components)/Profiles.svelte'
	import Languages from './(components)/Languages.svelte'
	import Personality from './(components)/Personality.svelte'
	import Interests from './(components)/Interests.svelte'

	const t = i18n({
		cs: {
			learning: 'učím se',
			skills: 'Dovednosti',
			summary: 'Profil',
			years: 'roky',
			experience_subtitle: 'Výběr',
			experience_title: 'Praxe',
		},
		en: {
			learning: 'learning',
			skills: 'Skills',
			summary: 'Summary',
			years: 'years',
			experience_subtitle: 'Selection',
			experience_title: 'Experience',
		},
	})
</script>

<article class="a4:px-12 relative px-6 py-8 print:shadow-none">
	<div class="text-secondary zoom-1.5 a4:absolute a4:right-12 mb-2 text-right *:p-1 *:before:content-none print:hidden">
		<LangSwitcher />
	</div>

	<section class="ml-2">
		<Title />
		<Contacts />
	</section>

	<section class="a4:grid a4:grid-cols-[auto_370px] mt-8 flex flex-col-reverse gap-10">
		<section class="border-secondary flex flex-col gap-3 rounded-xl bg-gray-100 px-4 pb-4">
			<h2>{t('summary')}</h2>

			<Lead />

			<h2 class="mt-1">{t('skills')}</h2>

			<SkillsHighlight />
			<SkillsTech />

			<h2 class="mt-1">Who I am</h2>

			<Personality />
			<Interests />
			<Languages />
			<Education />
			<Profiles />
		</section>

		<section>
			<h2 class="mt-1">{t('experience_title')}</h2>
			<div class="text-secondary zoom-[1.1]">{t('experience_subtitle')}</div>

			<Experience />
		</section>
	</section>
</article>
