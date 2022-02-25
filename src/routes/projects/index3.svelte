<script>

	const bp = [
		{
			title: "97' Trimaran", //wild thing
			description: 'Conversion to electric engines and solar',
			src: '/images/projects/boats/wild-thing/wild-thing-superior.jpg',
			href: '/projects/boats/wild-thing'
		},
		{
			title: "36' Larry Smith Scarab", 
			description: 'Custom speed boat',
			src: '/images/projects/boats/cigarette/b-cig-front.jpg',
			href: ''
		},
		{
			title: 'Ski Boat', //ski boat
			description: 'Small boat to rebuild for speed',
			src: '/images/projects/boats/ski-boat/ski-boat-front.jpg',
			href: '/projects/boats/ski-boat'
		},
		{
			title: "34' Welcraft Scarab", //masa scarab
			description: 'A fun medium sized boat',
			src: '/images/projects/boats/scarab/masa/masa-side.jpg',
			href: ''
		},
		{
			title: "28' Larry Smith Scarab", //singer scarab
			description: 'A fun sized medium boat',
			src: '/images/projects/boats/scarab/singer/singer-front.jpg',
			href: ''
		},
		{
			title: "41' Corsa", //41 scarab
			description: 'Beautiful long scarab to refurbish',
			src: '/images/projects/boats/scarab/41-scarab/41-scarab-front.jpg',
			href: ''
		}
	];

	const ap = [
		{
			title: "'98 385 Ferrari to Truck Conversion", //ferrari truck
			description: 'A salvaged Ferrari chassis to become the ultimate truck',
			src: '/images/projects/auto/ferrari/f-back.jpg',
			href: ''
		},
		{
			title: "'97 Hard-top Jaguar XK8", //98 jag x2
			description: 'One of two beautiful Jaguars to customize',
			src: '/images/projects/auto/jaguar/blue-jag-front.jpg',
			href: ''
		},
		{
			title: "'98 Convertible Jaguar XK8", //98 jag x2
			description: 'One of two beautiful Jaguars to customize',
			src: '/images/projects/auto/jaguar/red-jag-front.jpg',
			href: ''
		},
		{
			title: "'94 Honda Del Sol", //del sol
			description: 'Standard Del Sol to burn rubber',
			src: '/images/projects/auto/del-sol/del-sol-side.jpg',
			href: ''
		}
		
	];

	const lp = [
		{
			title: '40 Acre Skate Complex', //wisconsin track
			description: 'Spacious speed skating track in Wisconsin',
			src: '/images/projects/land/sstrack.jpg',
			href: ''
		}
	];

	const list = [
		{ name: 'Land Projects', abbr: lp },
		{ name: 'Boat Projects', abbr: bp },
		{ name: 'Auto Projects', abbr: ap }
	];
</script>

<section id="projects" class="p-5 otherpage">
	<h1 class="text-light">List of Projects</h1>
	<p class="text-light">Here you can find all of the family projects we are planning and working on</p>
	<hr class="text-light" />
	{#each list as li}
		<h1 class="text-light text-center">{li.name}</h1>
		<div class="row">
			{#each li.abbr as p}
				<div class="col-md-4 py-3 mw-600 mx-auto">
					<div class="card">
						<img class="card-img-top" src={p.src} alt={p.title} />
						<div class="card-body">
							<h4 class="card-title">{p.title}</h4>
							<p class="card-text">
								{p.description}
							</p>
							{#if p.href !== ''}
								<a href={p.href} class="btn btn-primary">Learn more</a>
							{/if}
						</div>
					</div>
				</div>
			{/each}
		</div>
		<hr class="text-light" />
	{/each}
</section>
