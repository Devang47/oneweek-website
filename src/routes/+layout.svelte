<script lang="ts">
	import '$lib/assets/styles/tailwind-output.css'
	import Toolbar from '$lib/components/Global/Toolbar.svelte'

	// @ts-ignore
	import NProgress from 'nprogress'
	import { navigating } from '$app/stores'

	// NProgress Loading bar
	import '$lib/assets/styles/nprogress.css'

	NProgress.configure({
		minimum: 0.75,
		showSpinner: false,
		speed: 5,
		trickleSpeed: 200
	})

	$effect(() => {
		if ($navigating) {
			NProgress.start()
		} else {
			NProgress.done()
		}
	})
</script>

<svelte:head>
	<link rel="stylesheet" href="/fonts/montserrat.css" />
</svelte:head>

<Toolbar />
<main class="w-screen overflow-hidden">
	<slot />
</main>

<style>
</style>
