<script lang="ts">
	const contactEmail = 'hi@supernumbers.cloud';
	const contactHref = `mailto:${contactEmail}?subject=${encodeURIComponent('Contact us')}`;

	const points = [
		{
			title: 'Past',
			label: 'What already happened',
			labelClass: 'border border-white/15 text-neutral-400',
			dotClass: 'border border-white/40 bg-neutral-950',
			body: 'Money in, money out, and where it went.'
		},
		{
			title: 'Present',
			label: 'Where you stand today',
			labelClass: 'border border-white bg-white text-neutral-950',
			dotClass: 'bg-white',
			body: 'Plain numbers, any time, from any device.'
		},
		{
			title: 'Future',
			label: 'What comes next',
			labelClass: 'border border-white text-white',
			dotClass: 'border border-white bg-neutral-950',
			body: 'Enough of a view to plan the step ahead.'
		}
	];
</script>

<svelte:head>
	<title>Accounting, made simple · Super Numbers Cloud</title>
	<meta
		name="description"
		content="See the past, the present, and what comes next. Simple accounting from Super Numbers Cloud."
	/>
	<meta property="og:title" content="Accounting, made simple · Super Numbers Cloud" />
	<meta
		property="og:description"
		content="See the past, the present, and what comes next. Simple accounting for your business."
	/>
	<meta property="og:type" content="website" />
</svelte:head>

<div class="flex min-h-screen flex-col bg-neutral-950 font-sans text-neutral-100 antialiased">
	<header class="mx-auto flex w-full max-w-3xl items-center justify-between px-6 py-5">
		<span class="font-brand text-base font-semibold tracking-tight">Super Numbers Cloud</span>
		<a
			href={contactHref}
			class="rounded-full border border-white/15 px-4 py-2 text-sm font-medium transition hover:border-white/40"
		>
			Contact us
		</a>
	</header>

	<main>
		<section
			class="motion-safe:animate-fade-up mx-auto max-w-3xl px-6 pt-12 pb-10 text-center md:pt-16"
		>
			<h1
				class="font-display text-4xl leading-tight font-semibold tracking-tight text-balance text-white sm:text-5xl"
			>
				Accounting, made simple.
			</h1>
			<p class="mx-auto mt-4 max-w-xl text-lg leading-relaxed text-neutral-400">
				See the past, the present, and what comes next. Easy to start, easy to use, every day.
			</p>
			<a
				href={contactHref}
				class="mt-6 inline-block rounded-full bg-white px-7 py-3 font-medium text-neutral-950 transition hover:bg-neutral-200"
			>
				Contact us
			</a>
		</section>

		<section class="mx-auto max-w-3xl px-6 pb-12 text-center">
			<ol class="relative grid gap-8 md:grid-cols-3 md:gap-0">
				<span
					class="absolute top-[5px] right-[16.666%] left-[16.666%] hidden h-px bg-white/15 md:block"
					aria-hidden="true"
				></span>
				{#each points as point (point.title)}
					<li class="relative flex flex-col items-center px-3 md:pt-8">
						<span
							class="mb-3 size-[11px] rounded-full md:absolute md:top-0 md:left-1/2 md:mb-0 md:-translate-x-1/2 {point.dotClass}"
							aria-hidden="true"
						></span>
						<h2 class="font-display text-sm font-medium text-neutral-500">{point.title}</h2>
						<p class="mt-3">
							<span
								class="inline-block rounded-full px-3 py-1 text-sm font-medium {point.labelClass}"
							>
								{point.label}
							</span>
						</p>
						<p class="mt-3 text-sm leading-relaxed text-neutral-400">{point.body}</p>
					</li>
				{/each}
			</ol>
		</section>
	</main>

	<footer
		class="mx-auto flex w-full max-w-3xl flex-col gap-2 px-6 py-6 text-sm text-neutral-500 sm:flex-row sm:justify-between"
	>
		<p class="font-brand">© {new Date().getFullYear()} Super Numbers Cloud</p>
		<a href="mailto:{contactEmail}" class="transition hover:text-white">{contactEmail}</a>
	</footer>
</div>
