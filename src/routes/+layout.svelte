<script lang="ts">
	import { page } from '$app/stores';
	import '../app.postcss';
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';
</script>

<!-- App Shell -->
<AppShell>
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar>
			<svelte:fragment slot="lead">
				<a href="/#home">
					<img src="./logo-loka-amber.png" alt="logo" class="w-20 ml-16 hover:cursor-pointer" />
				</a>
			</svelte:fragment>
			<svelte:fragment slot="trail">
				<div class="flex gap-5 mr-16">
				<ul class="list gap-5 hidden lg:flex">
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
						<a class:active={ $page.url.hash === "#team"} href="/#team" aria-label="contact">Team</a>
					</li>
					<li class=" hover:text-[#fbbf24] hover:cursor-pointer">
						<a class:active={ $page.url.hash === "#contact"} href="/#contact" aria-label="contact">Contact Us</a>
					</li>
					<li class=" hover:text-[#fbbf24] hover:cursor-pointer">
						<a id="about" class:active={ $page.url.hash === "/about"} href="/about#clients" aria-label="about">About</a>
					</li>
				</ul>
				<a
					class="btn btn-sm variant-ghost-surface hover:text-[#fbbf24]"
					href="https://accounts.zoho.com/signin?servicename=VirtualOffice&signupurl=https://www.zoho.com/mail/zohomail-pricing.html&serviceurl=https://mail.zoho.com"
					target="_blank"
					rel="noreferrer"
				>
					Staff Email
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

	#about:active::after {
		content: '';
		width: 12px;
		height: 12px;
		background-color: yellow;
		border-radius: 50%;
	}
</style>
