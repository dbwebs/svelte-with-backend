<script lang="ts">
	import { page } from '$app/stores';
	import logo from './Team-X-small.png';

	import fbicon from './social-icons/webicon-facebook.png';
	import igicon from './social-icons/webicon-instagram.png';
	import yticon from './social-icons/webicon-youtube.png';

	import { onMount, SvelteComponent } from 'svelte';

	// Show mobile icon and display menu
	let showMobileMenu = false;
	let loading = false;

	// List of navigation items
	const navItems = [
		{ label: 'Home', href: '/' },
		{ label: 'About', href: '/about' },
		{ label: 'Contacts', href: '/contacts' },
		{ label: 'Articles', href: '/articles' },
		{ label: 'Projects', href: '/projects' },
		{ label: 'Jason Scott Lee', href: '/jason-scott-lee' },
		{ label: 'Posts', href: '/post' }
	];

	// Mobile menu click event handler
	const handleMobileIconClick = () => {
		showMobileMenu = !showMobileMenu;
	};

	// Media match query handler
	const mediaQueryHandler = (e) => {
		// Reset mobile state
		if (!e.matches) {
			showMobileMenu = false;
		}
	};

	// Attach media query listener on mount hook
	onMount(() => {
		const mediaListener = window.matchMedia('(max-width: 767px)');

		mediaListener.addListener(mediaQueryHandler);
	});

	
	
</script>

<header class="none">
	<ul class="sticky-social-bar">
		<li class="social-bar-item">
			<a
				class="social-link-text social-icon-text"
				href="https://www.facebook.com/Team-X-Hawaii-440674386271922">Facebook</a
			><a
				class="icon-link"
				href="https://www.facebook.com/Team-X-Hawaii-440674386271922"
				aria-hidden="true"><img class="social-icon" alt="facebook icon" src={fbicon} /></a
			>
		</li>
		<li class="social-bar-item">
			<a
				class="social-link-text social-icon-text"
				href="https://www.youtube.com/channel/UC41XLCvW2Uh6YlOsmfAZRww">Youtube</a
			><a
				class="icon-link"
				href="https://www.youtube.com/channel/UC41XLCvW2Uh6YlOsmfAZRww"
				aria-hidden="true"><img class="social-icon" alt="youtube icon" src={yticon} /></a
			>
		</li>
		<li class="social-bar-item">
			<a class="social-link-text social-icon-text" href="https://www.instagram.com/teamxhawaii"
				>Instagram</a
			><a class="icon-link" href="https://www.instagram.com/teamxhawaii" aria-hidden="true"
				><img class="social-icon" alt="instagram icon" src={igicon} /></a
			>
		</li>
	</ul>

	<nav>
		<div class="inner">
			<div on:click={handleMobileIconClick} class={`mobile-icon${showMobileMenu ? ' active' : ''}`}>
				<div class="middle-line" />
			</div>
			<ul class={`navbar-list${showMobileMenu ? ' mobile' : ''}`}>
				<li>
					<a href="https://www.xarbinindustries.com"
						><img class="nav-logo" src={logo} alt="Logo" /></a
					>
				</li>
				{#each navItems as item}
					<li>
						<a href={item.href}>{item.label}</a>
					</li>
				{/each}
			</ul>
		</div>
	</nav>
	<!-- <nav class="navbar navbar-expand-lg navbar-dark bg-primary">
		<div class="container-fluid">
		 <a class="navbar-brand" href="#">Brand</a>
		 <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#main_nav"  aria-expanded="false" aria-label="Toggle navigation">
			 <span class="navbar-toggler-icon"></span>
		 </button>
		 <div class="collapse navbar-collapse" id="main_nav">
		   <ul class="navbar-nav">
			   <li class="nav-item active"> <a class="nav-link" href="#">Home </a> </li>
			   <li class="nav-item"><a class="nav-link" href="#"> About </a></li>
			   <li class="nav-item"><a class="nav-link" href="#"> Services </a></li>
			   <li class="nav-item dropdown">
				  <a class="nav-link  dropdown-toggle" href="#" data-bs-toggle="dropdown">  Hover me  </a>
				   <ul class="dropdown-menu">
					 <li><a class="dropdown-item" href="#"> Submenu item 1</a></li>
					 <li><a class="dropdown-item" href="#"> Submenu item 2 </a></li>
					 <li><a class="dropdown-item" href="#"> Submenu item 3 </a></li>
				   </ul>
			   </li>
		   </ul>
		 </div> 
		</div> 
	   </nav> -->
</header>
