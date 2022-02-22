<script context="module">
	const wt = '/images/projects/boats/wild-thing/wild-thing-superior.jpg';
	const xiia = '/images/portrait/Xiia.png';
	const miah = '/images/portrait/Miah.png';
	const anna = '/images/portrait/Anna.png';
	const zakayla = '/images/portrait/Zakayla.png';
	const makailah = '/images/portrait/Makailah.png';

	const famList = [
		{ name: 'Stacy', title: 'Father and Coach', src: miah },
		{ name: 'Roni', title: 'Mother and Teacher', src: zakayla },
		{ name: 'Xion', title: 'Daughter and Athlete', src: xiia },
		{ name: 'Zephaneah', title: 'Daughter and Athlete', src: anna },
		{ name: 'Natasha', title: 'Daughter and Athlete', src: miah },
		{ name: 'Makailah', title: 'Daughter and Athlete', src: makailah },
		{ name: 'Neahmiah', title: 'Son and Athlete', src: miah },
		{ name: 'Annastasiah', title: 'Daughter and Athlete', src: anna },
		{ name: 'Zakayla', title: 'Daughter and Athlete', src: zakayla },
		{ name: 'Xalia', title: 'Daughter and Athlete', src: makailah },
		{ name: 'Zemikah', title: 'Daughter and Athlete', src: zakayla },
		{ name: 'Xiia', title: 'Daughter and Athlete', src: xiia },
		{ name: 'Mekah', title: 'Grandaughter and Athlete', src: makailah }
	];
</script>

<svelte:head>
	<title>About</title>
</svelte:head>

<section id="about" class="otherpage">
	<div class="row">
		{#each famList as member}
			<div class="col-md-6 p-5">
				<div class="card r mw-600 mx-auto">
					<img class="card-img-top rounded" src={member.src} alt={member.name} />
					<div class="card-img-overlay card-inverse">
						<h4 class="text-stroke overlay-text mw-200 ta-center">
							{member.name}
						</h4>

						<p class="card-br mw-200 bg-primary p-1 overlay-text">{member.title}</p>
					</div>
				</div>
			</div>
		{/each}
	</div>
</section>
