<script>
import Project from '../pcontent.svelte';


	const wts = '/images/projects/boats/wild-thing/wild-thing-superior.jpg';
	const wtadh = '/images/projects/boats/wild-thing/wt-and-dh.jpg';
	const wtp = '/images/projects/boats/wild-thing/wt-posterior.jpg';
	const txowt = '/images/projects/boats/wild-thing/Team-X-on-wt.jpg';
	
	const heroimg = 
	{
		img: txowt,
		alt: 'Team X on the wild thing'
	}

	const info =
	{
		titleA: 'The Wild Thing Project',
		titleB: 'The Build',
		titleBsub:'Hybrid Engine Conversion'
	}

	const nowinfo = [
		{ content: "97' hybrid high-speed multi-hull yacht" },
		{ content: "Loa: 97'" },
		{ content: "Beam: 36'" },
		{ content: 'Hull material: composite' },
		{ content: 'Design speed: 50 knots' },
		{ content: 'Current engines: 3 Caterpillar 3412TA diesel' },
		{ content: 'Total horesepower: 3750' },
		{ content: 'Drives: 3 - surface piercing' }
	];

	const prinfo = [
		{ content: 'Convert to 3 main electric engines; undecided manufacturer' },
		{ content: 'Projected horsepower/Kilowatts: 4500hp/3355.65kw' },
		{ content: 'Projected speed: 60 knots' },
		{ content: 'Secondary power source: Generator' },
		{ content: 'Main power source: Solar panels + High-capacity batteries' },
		{ content: 'Auxilliary Power Unit: Turbine' },
		{ content: 'Replace aero wing with a delta, low-speed/high-lift wing with more surface area' },
		{ content: 'Modify hulls to reduce hydro friction' },
		{ content: 'Modify superstructure for efficient aerodynamics and more useable space' }
	];
</script>

<section id="wild-thing">
	<Project {info} {heroimg} {nowinfo} {prinfo}/>
</section>
