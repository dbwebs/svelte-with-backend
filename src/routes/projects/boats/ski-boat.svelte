<script>
    import Project from '../pcontent.svelte';

    const sbf = '/images/projects/boats/ski-boat/ski-boat-front.jpg';
    const sbb = '/images/projects/boats/ski-boat/ski-boat-back.jpg';
    const sbt = '/images/projects/boats/ski-boat/ski-boat-top.jpg';

    const info = {
        titleA: 'Ski-boat',
        titleB: 'The Build',
        titleBsub: 'Refurbish'};

    const heroimg =
    {
        img: sbt,
        alt: 'Top of ski boat'
    }

    const nowinfo = [
		{ content: "Small US open towboat" },
		{ content: "Missing interior components" }
	];

	const prinfo = [
		{ content: 'Fix and replace interior components' },
		{ content: 'Fix or replace engine' }
	];
</script>

<section id="ski-boat">
    <Project {info} {heroimg} {nowinfo} {prinfo}/>
</section>