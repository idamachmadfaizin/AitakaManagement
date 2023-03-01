<script lang="ts">
	import { page } from '$app/stores';
	import {
		Sidebar,
		SidebarDropdownItem,
		SidebarDropdownWrapper,
		SidebarGroup,
		SidebarItem,
		SidebarWrapper
	} from 'flowbite-svelte';
	import { children } from 'svelte/internal';
	import ChartPieIcon from './icons/heroicons/ChartPieIcon.svelte';
	import Squares2x2Icon from './icons/heroicons/Squares2x2Icon.svelte';

	interface ISidebarItem {
		label: string;
		activeUrl: string;
		iconComponent?: any;
		children?: Omit<ISidebarItem, 'children' | 'iconComponent'>[];
	}

	$: activeUrl = $page.url.pathname;

	const iconClass = 'w-6 h-6';
	let spanClass = 'flex-1 ml-3 whitespace-nowrap';

	let sideBarItems: ISidebarItem[] = [
		{
			label: 'Dashboard',
			activeUrl: '/',
			iconComponent: ChartPieIcon
		},
		{
			label: 'Products',
			activeUrl: '/products',
			iconComponent: Squares2x2Icon
		},
		{
			label: 'Order',
			activeUrl: '/order',
			iconComponent: ChartPieIcon
		}
	];
</script>

<Sidebar class={$$props.class}>
	<SidebarWrapper class="h-full rounded-none">
		<SidebarGroup>
			{#each sideBarItems as sideBar (sideBar.activeUrl)}
				{#if sideBar.children && sideBar.children.length > 0}
					<SidebarDropdownWrapper label={sideBar.label}>
						<svelte:fragment slot="icon">
							<svelte:component this={sideBar.iconComponent} class={iconClass} />
						</svelte:fragment>
						{#each sideBar.children as child (child.activeUrl)}
							<SidebarDropdownItem label={child.label} active={activeUrl === child.activeUrl} />
						{/each}
					</SidebarDropdownWrapper>
				{:else}
					<SidebarItem label={sideBar.label} href={sideBar.activeUrl} active={activeUrl === sideBar.activeUrl}>
						<svelte:fragment slot="icon">
							<svelte:component this={sideBar.iconComponent} class={iconClass} />
						</svelte:fragment>
					</SidebarItem>
				{/if}
			{/each}
		</SidebarGroup>
	</SidebarWrapper>
</Sidebar>
