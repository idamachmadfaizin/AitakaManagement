<script lang="ts">
	import { DarkMode, Navbar, NavBrand, NavHamburger, Tooltip } from 'flowbite-svelte';
	import { createEventDispatcher } from 'svelte';
	import MoonIcon from './icons/heroicons/MoonIcon.svelte';
	import SunIcon from './icons/heroicons/SunIcon.svelte';

	const dispatch = createEventDispatcher();

	function navHamburgerClick() {
		dispatch('navHamburgerClick');
	}
</script>

<Navbar fluid={true} class={$$props.class}>
	<div class="flex">
		<NavHamburger btnClass="mr-3" on:click={navHamburgerClick} />
		<NavBrand href="/">
			<img src="/favicon.png" class="mr-3 h-6 sm:h-9" alt="Logo" />
			<span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white">
				Logo name
			</span>
		</NavBrand>
	</div>

	<!-- <NavUl>
		<NavLi href="/" active={true}>Home</NavLi>
		<NavLi href="/about">About</NavLi>
		<NavLi href="/services">Services</NavLi>
		<NavLi href="/pricing">Pricing</NavLi>
		<NavLi href="/contact">Contact</NavLi>
	</NavUl> -->

	<div>
		<DarkMode>
			<svelte:fragment slot="lightIcon">
				<MoonIcon class="w-5 h-5" fill="currentColor" />
			</svelte:fragment>
			<svelte:fragment slot="darkIcon">
				<SunIcon class="w-5 h-5" fill="currentColor" />
			</svelte:fragment>
		</DarkMode>
		<Tooltip placement="bottom">
			{localStorage.getItem('color-theme') === 'dark' ? 'Dark mode' : 'Light mode'}
		</Tooltip>
	</div>
</Navbar>
