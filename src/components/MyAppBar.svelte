<script lang="ts">
	import { DarkMode, Navbar, NavBrand, NavHamburger, Tooltip } from 'flowbite-svelte';
	import { createEventDispatcher } from 'svelte';

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
		<DarkMode />
		<Tooltip placement="bottom">
			{localStorage.getItem('color-theme') === 'dark' ? 'Toggle light mode' : 'Toggle dark mode'}
		</Tooltip>
	</div>
</Navbar>
