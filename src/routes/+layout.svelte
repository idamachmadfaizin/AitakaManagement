<script lang="ts">
	import { Card } from 'flowbite-svelte';

	// import '../app.css';
	import MyAppBar from '../components/MyAppBar.svelte';
	import MySidebar from '../components/MySidebar.svelte';

	var copyRightYear = new Date().getUTCFullYear();
	let open = true;

	function appBarMenuClicked() {
		open = !open;
	}
</script>

<div class="flex flex-col min-h-screen">
	<MyAppBar on:navHamburgerClick={appBarMenuClicked} class="z-0 shadow-sm" />

	<div class="flex flex-grow">
		{#if open}
			<MySidebar />
		{/if}

		<div class="flex flex-col flex-grow">
			<main class="box-border flex flex-col flex-grow w-full p-6 mx-auto my-0 dark:bg-gray-700">
				<slot />
			</main>

			<footer
				class="flex flex-col items-center justify-center p-3 bg-gray-100 dark:bg-gray-800 dark:text-white"
			>
				© Aitaka Management {copyRightYear}
			</footer>
		</div>
	</div>
</div>

<style type="scss">
	@import '../app.scss';
</style>
