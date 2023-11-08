<script lang="ts">
	import { page } from '$app/stores';
	import '../app.postcss';
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';
	import { initializeStores } from '@skeletonlabs/skeleton';

	import { Drawer, getDrawerStore } from '@skeletonlabs/skeleton';
    import type { DrawerSettings, DrawerStore } from '@skeletonlabs/skeleton';

	initializeStores();

	 const drawerStore = getDrawerStore();

	 
const drawerSettings: DrawerSettings = {
	id: 'example-3',
	// Provide your property overrides:
	// bgDrawer: 'bg-[#434c5a]',
	bgDrawer: 'bg-[#060a09]',
	width: 'w-[75%]',
};

	let menuOpen = false

	function toggleMenu(){
		menuOpen = !menuOpen
	}

	function openMenuLayout(){
		//drawerStore.open()
		drawerStore.open(drawerSettings);
		toggleMenu()
	}

	function closeMenuLayout(){
		drawerStore.close()
		toggleMenu()
	}

</script>



<Drawer zIndex='z-10' on:backdrop={ toggleMenu } opacityTransition={true} transitions duration={500}>
	<ul class="mt-32 flex flex-col justify-center items-center text-3xl gap-y-10 text-white">
		<li class=" hover:text-[#fbbf24] hover:cursor-pointer">
			<a class:active={ $page.url.hash === "#home"} href="/#home" aria-label="home" on:click={closeMenuLayout} >Home</a>
		</li>
		<li class=" hover:text-[#fbbf24] hover:cursor-pointer">
			<a class:active={ $page.url.hash === "#services"} href="/#services" aria-label="services" on:click={closeMenuLayout} >Services</a>
		</li>
		<li class=" hover:text-[#fbbf24] hover:cursor-pointer">
			<a class:active={ $page.url.hash === "#engagements"} href="/#engagements" aria-label="engagements" on:click={closeMenuLayout}>Engagements</a>
		</li>
		<li class=" hover:text-[#fbbf24] hover:cursor-pointer">
			<a class:active={ $page.url.hash === "#faqs"} href="/#faqs" aria-label="faqs" on:click={closeMenuLayout}>FAQs</a>
		</li>
		<li class=" hover:text-[#fbbf24] hover:cursor-pointer">
			<a class:active={ $page.url.hash === "#testimonials"} href="/#testimonials" aria-label="testimonials" on:click={closeMenuLayout}>Testimonials</a>
		</li>
		<li class=" hover:text-[#fbbf24] hover:cursor-pointer">
			<a class:active={ $page.url.hash === "#team"} href="/#team" aria-label="team" on:click={closeMenuLayout}>Team</a>
		</li>
		<li class=" hover:text-[#fbbf24] hover:cursor-pointer">
			<a class:active={ $page.url.hash === "#contact"} href="/#contact" aria-label="contact" on:click={closeMenuLayout}>Contact Us</a>
		</li>
		<li class=" hover:text-[#fbbf24] hover:cursor-pointer">
			<a class:active={ $page.url.pathname === "/about"} href="/about" aria-label="about" on:click={closeMenuLayout}>About</a>
		</li>
	</ul>
</Drawer>


<!-- App Shell -->
<AppShell>
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar>
			<svelte:fragment slot="lead">
				{#if menuOpen}
					<button class="ml-4 text-3xl lg:hidden z-50" on:click={ closeMenuLayout }>&#10005</button>
				{:else}
					<button class="ml-4 text-3xl lg:hidden z-50" on:click={ openMenuLayout }>&#9776</button>
				{/if}
				<a href="/#home" class="hidden lg:block">
					<img src="./logo-loka-amber.png" alt="logo" class="h-16 lg:w-20 lg:ml-16 hover:cursor-pointer" />
				</a>
			</svelte:fragment>
			<svelte:fragment slot="trail">
				<div class="flex gap-5 mr-16">
				<ul class="list gap-5 hidden lg:flex mr-5">
					<li class=" hover:text-[#fbbf24] hover:cursor-pointer">
						<a class:active={ $page.url.hash === "#home"} href="/#home" aria-label="home" >Home</a>
					</li>
					<li class=" hover:text-[#fbbf24] hover:cursor-pointer">
						<a class:active={ $page.url.hash === "#services"} href="/#services" aria-label="services" >Services</a>
					</li>
					<li class=" hover:text-[#fbbf24] hover:cursor-pointer">
						<a class:active={ $page.url.hash === "#engagements"} href="/#engagements" aria-label="engagements">Engagements</a>
					</li>
					<li class=" hover:text-[#fbbf24] hover:cursor-pointer">
						<a class:active={ $page.url.hash === "#faqs"} href="/#faqs" aria-label="faqs">FAQs</a>
					</li>
					<li class=" hover:text-[#fbbf24] hover:cursor-pointer">
						<a class:active={ $page.url.hash === "#testimonials"} href="/#testimonials" aria-label="testimonials">Testimonials</a>
					</li>
					<li class=" hover:text-[#fbbf24] hover:cursor-pointer">
						<a class:active={ $page.url.hash === "#team"} href="/#team" aria-label="team">Team</a>
					</li>
					<li class=" hover:text-[#fbbf24] hover:cursor-pointer">
						<a class:active={ $page.url.hash === "#contact"} href="/#contact" aria-label="contact">Contact Us</a>
					</li>
					<li class=" hover:text-[#fbbf24] hover:cursor-pointer">
						<a class:active={ $page.url.pathname === "/about"} href="/about" aria-label="about">About</a>
					</li>
				</ul>
				<a
					class="btn btn-sm variant-ghost-surface hidden lg:block hover:text-[#fbbf24]"
					href="https://accounts.zoho.com/signin?servicename=VirtualOffice&signupurl=https://www.zoho.com/mail/zohomail-pricing.html&serviceurl=https://mail.zoho.com"
					target="_blank"
					rel="noreferrer"
				>
					Staff Email
				</a>
				<a href="/#home" class="lg:hidden">
					<img src="./logo-loka-amber.png" alt="logo" class="ml-4 h-16 lg:w-20 lg:ml-16 hover:cursor-pointer" />
				</a>
				</div>
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>

<style>
	.active{
		text-decoration-line: underline;
		text-decoration-thickness: 4px;
		text-decoration-color: #fbbf24;
		text-underline-position: under;
		-ms-text-underline-position: under;
	}
</style>
