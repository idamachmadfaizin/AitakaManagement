<script lang="ts">
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
	<MyAppBar on:navHamburgerClick={appBarMenuClicked} class="shadow-sm z-0" />

	<div class="flex flex-grow">
		{#if open}
			<MySidebar />
		{/if}

		<div class="flex flex-col flex-grow">
			<main class="flex flex-grow flex-col p-6 box-border my-0 mx-auto w-full dark:bg-gray-700">
				<slot />
			</main>

			<footer
				class="flex flex-col justify-center items-center p-3 bg-gray-100 dark:bg-gray-800 dark:text-white"
			>
				© Aitaka Management {copyRightYear}
			</footer>
		</div>
	</div>
</div>

<style type="scss">
	@import '../app.scss';
</style>
