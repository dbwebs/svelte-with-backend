<script context="module" lang="ts">
	import HeroSection from '$lib/sections/hero/HeroSection.svelte';
	import WelcomeSection from '$lib/sections/welcome/Welcome.svelte';
	import Posts from './post/index.svelte';

</script>

<svelte:head>
	<title>Home</title>
	<script src="https://kit.fontawesome.com/6245179c2f.js" crossorigin="anonymous"></script>
</svelte:head>

<section id="home" class="otherpage">
	<HeroSection />
	<WelcomeSection />
	
</section>
