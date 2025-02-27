<script lang="ts">
	import { page } from '$app/state'
	import Title from '$lib/components/organisms/Title.svelte'
	import SkillsHighlight from '$lib/components/organisms/SkillsHighlight.svelte'
	import History from '$lib/components/organisms/History.svelte'
	import Projects from '$lib/components/organisms/Projects.svelte'
	import Links from '$lib/components/organisms/Links.svelte'
	import SkillsInDetail from '$lib/components/organisms/SkillsInDetail.svelte'
	import Lead from '$lib/components/organisms/Lead.svelte'
	import Contacts from '$lib/components/organisms/Contacts.svelte'
	import Education from '$lib/components/organisms/Education.svelte'
	import LangSwitcher from '$lib/components/atoms/LangSwitcher.svelte'
	import { type Lang, Langs } from '$lib/langs'
	import { DEFAULT_LANG } from '$lib/constants'

	const langs = Object.keys(Langs) as Lang[]
	const currentLang = $derived(page.params.lang || DEFAULT_LANG) as Lang
</script>

<article class="px-6 py-8 a4:px-12 a4:shadow-2xl print:shadow-none">
	<nav
		class="text-secondary zoom-[1.5] mb-2 text-right *:p-1 *:before:content-none a4:absolute a4:right-12 print:hidden"
	>
		<LangSwitcher {langs} current={currentLang} />
	</nav>

	<Title />

	<section class="my-5 flex flex-col a4:flex-row-reverse a4:gap-10">
		<Contacts />
		<Lead />
	</section>

	<section class="flex flex-col-reverse gap-8 a4:grid a4:grid-cols-[380px_auto]">
		<div class="grid grid-cols-[200px_auto] content-start gap-x-4">
			<section class="col-span-2">
				<Projects />
			</section>

			<section class="col-span-2 a4:col-span-1">
				<History />
			</section>

			<div class="col-span-2 a4:col-span-1">
				<Education />
				<Links />
			</div>
		</div>

		<div class="border-secondary rounded border-2 border-dashed px-6 py-4">
			<SkillsHighlight />
			<SkillsInDetail />
		</div>
	</section>
</article>
