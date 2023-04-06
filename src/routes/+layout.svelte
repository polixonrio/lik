<script lang="ts">
	import '../app.postcss';
	import { onMount } from 'svelte';
	import {
		DarkMode,
		Dropdown,
		Chevron,
		Navbar,
		NavBrand,
		DropdownDivider,
		DropdownItem,
		NavLi,
		NavUl,
		NavHamburger,
		Button,
		Input
	} from 'flowbite-svelte';
	import {
		Footer,
		FooterBrand,
		FooterLinkGroup,
		FooterLink,
		FooterCopyright,
		FooterIcon
	} from 'flowbite-svelte';

	let active = 0;

	function setActive(index: number) {
		active = index;
	}

	let isOpen = false;
	let arrowClass = '';

	function toggleDropdown() {
		isOpen = !isOpen;
		arrowClass = isOpen ? 'arrow-up' : '';
	}

	let breakPoint: number = 1024;
	let width: number;
	let activateClickOutside = true;
	let drawerHidden: boolean = false;
	$: if (width >= breakPoint) {
		drawerHidden = false;
		activateClickOutside = false;
	} else {
		drawerHidden = true;
		activateClickOutside = true;
	}
	onMount(() => {
		if (width >= breakPoint) {
			drawerHidden = false;
			activateClickOutside = false;
		} else {
			drawerHidden = true;
			activateClickOutside = true;
		}
	});
	let darkmodebtn =
		'text-gray-500 dark:text-gray-400 hover:bg-gray-100 dark:hover:bg-gray-700 focus:outline-none focus:ring-4 focus:ring-gray-200 dark:focus:ring-gray-700 rounded-lg text-lg p-2.5  right-2 top-12  md:top-3 md:right-2 z-50';
	let divClass = 'w-full md:block md:w-auto';
	let ulClass =
		'flex flex-col p-4 text-center mt-4 md:flex-row md:space-x-8 md:mt-0 md:text-lg md:font-medium';
</script>

<svelte:window bind:innerWidth={width} />

<header class="sticky shadow-xl dark:shadow-indigo-500/50 top-0 z-50 ">
	<Navbar let:hidden let:toggle class="">
		<NavBrand href="/" class="">
			<img src="/images/logos.webp" class="h-auto mx-auto  w-9 md:w-9 lg:w-9" alt="mission" />
			<span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white ">
				Asterisc.in
			</span>
		</NavBrand>
		<div class="flex md:order-2">
		
			  <div class="hidden relative md:block">
				<div class="flex absolute inset-y-0 left-0 items-center pl-3 pointer-events-none">
				  <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 dark:text-white"><path stroke-linecap="round" stroke-linejoin="round" d="M21 21l-5.197-5.197m0 0A7.5 7.5 0 105.196 5.196a7.5 7.5 0 0010.607 10.607z" /></svg>
				</div>
				<Input  id="search-navbar" class="pl-10" placeholder="Search..." />
			  </div>

			<DarkMode class="ml-2" btnClass={darkmodebtn} />
			<NavHamburger on:click={toggle} />
		</div>

		<NavUl {hidden} {divClass} {ulClass}>
			<Input id="search-navbar" class="pl-10 mb-3 sm:hidden" placeholder="Search..." />
			<NavLi href="/" active={true}>Home</NavLi>
			<NavLi id="nav-menu1" class="cursor-pointer ">
				Automation
			</NavLi>
			<NavLi id="nav-menu2" class="cursor-pointer ">
				Development
			</NavLi>
			<NavLi id="nav-menu3" class="cursor-pointer ">
				Projects
			</NavLi>
			<NavLi id="nav-menu4" class="cursor-pointer ">
				Programs
			</NavLi>
			<NavLi href="/services">Services</NavLi>
			<NavLi href="/pricing">Pricing</NavLi>
			<NavLi href="/contact">Contact</NavLi>
			<Dropdown triggeredBy="#nav-menu1" class="w-44 z-20">
				<DropdownItem>Selenium Tutorial</DropdownItem>
				<DropdownItem>Selenium Web Driver With Java</DropdownItem>
				<DropdownItem>Selenium Web Driver With C#</DropdownItem>
				<DropdownItem>Katalon Studio</DropdownItem>
				<DropdownItem>Puppeteer and Jest</DropdownItem>
			</Dropdown>
			<Dropdown triggeredBy="#nav-menu2" class="w-44 z-20">
				<DropdownItem>Java Tutorial</DropdownItem>
				<DropdownItem>JSP Tutorial</DropdownItem>
				<DropdownItem>Servelet Tutorial</DropdownItem>
				<DropdownItem>Spring Tutorial</DropdownItem>
				<DropdownItem>Hibernate Tutorial</DropdownItem>
				<DropdownItem>Spring Boot With ReactJS</DropdownItem>
				<DropdownItem>Angular JS</DropdownItem>
			</Dropdown>
			<Dropdown triggeredBy="#nav-menu3" class="w-44 z-20">
				<DropdownItem>Java Projects</DropdownItem>
				<DropdownItem>Hibernate Projects</DropdownItem>
				<DropdownItem>Spring Projects</DropdownItem>
				<DropdownItem>PHP Projects</DropdownItem>
				<DropdownItem>UML Diagrams</DropdownItem>
			</Dropdown>
			<Dropdown triggeredBy="#nav-menu4" class="w-44 z-20">
				<DropdownItem>Java Programs</DropdownItem>
				<DropdownItem>VB Programs</DropdownItem>
				<DropdownItem>C# Programs</DropdownItem>
				<DropdownDivider />
				<DropdownItem>Sign out</DropdownItem>
			</Dropdown>
		</NavUl>
	</Navbar>
</header>

<main>
	<slot />
</main>

<Footer footerType="socialmedia">
	<div class="mx-auto max-w-screen-xl text-center">
		<FooterBrand
			href="https://asterisc.in"
			src="/images/logos.webp"
			alt="Asterisc Logo"
			name="Asterisc.in"
			aClass="flex justify-center items-center text-2xl font-semibold text-gray-900 dark:text-white"
		/>

		<p class="my-6 text-gray-500 dark:text-gray-400">Join us now for your better tomorrow.</p>
		<FooterLinkGroup
			ulClass="flex flex-wrap justify-center items-center mb-6 text-gray-900 dark:text-white"
		>
			<FooterLink liClass="" aClass="mr-4 hover:underline md:mr-6" href="/">About Us</FooterLink>
			<FooterLink liClass="" aClass="mr-4 hover:underline md:mr-6" href="/">FAQs</FooterLink>
			<FooterLink liClass="" aClass="mr-4 hover:underline md:mr-6" href="/">Testimonials</FooterLink
			>
			<FooterLink liClass="" aClass="mr-4 hover:underline md:mr-6" href="/">Projects</FooterLink>

			<FooterLink liClass="" aClass="mr-4 hover:underline md:mr-6" href="/">Contact Us</FooterLink>
		</FooterLinkGroup>
		<span class="text-sm text-gray-500 sm:text-center dark:text-gray-400"
			>© 2021-2023 <a href="https://asterisc.in/" class="hover:underline">Asterisc.in™ </a>.
			Developed by Asterisc Technocrat Pvt. Ltd. All Rights Reserved.</span
		>
	</div>
</Footer>

<style>
	.arrow {
		transition: transform 0.2s ease-in-out;
		transform-origin: center center;
	}

	.arrow-up {
		transform: rotate(180deg);
	}
</style>
