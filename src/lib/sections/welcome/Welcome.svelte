<script lang="ts">
	const welcomeCards = [
		{
			heading: 'Articles',
			src: '/images/health/veggie-pic.jpg',
			href: '/articles',
			content: 'What we have to say about health, skating, and other topics'
		},
		{
			heading: 'Projects',
			src: '/images/projects/boats/wild-thing/wild-thing-superior.jpg',
			href: '/projects',
			content: 'See what we are working on currently and our future projects'
		},
		{
			heading: 'Jason Scott Lee',
			src: '/images/jason-scott-lee/jsllandscape.jpg',
			href: '/jason-scott-lee',
			content: 'A close family friend who is co-producer and the voice of the production'
		}
	];
</script>

<section id="welcome" class="container-fluid">
	<div class="row">
		<div class="col-md-7 p-5 text-center">
			<h2>Welcome to our website!</h2>
			<p>
				Team X Hawaii is a reality TV show project to encourage the healthy and fun sport of speed
				skating.<br />Keep up to date with all of our current and upcoming projects here!
			</p>
		</div>
		<div class="col-md-5 p-5">
			<h3>How to navigate</h3>
			<p>
				Check out the top bar for specific sections, scroll through the homepage to get the latest,
				or get a quick start with one of the links below.
			</p>
		</div>
	</div>
	<div class="row">
		{#each welcomeCards as item}
			<div class="col-md-4 py-3 mw-600">
				<div class="card">
					<img class="card-img-top" src={item.src} alt={item.heading} />
					<div class="card-body">
						<h4 class="card-title">{item.heading}</h4>
						<p class="card-text">
							{item.content}
						</p>
						<a href={item.href} class="btn btn-primary">Learn more</a>
					</div>
				</div>
			</div>
		{/each}
</section>
