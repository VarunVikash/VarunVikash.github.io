<script>
	import ProjectHeader from '$lib/components/ProjectHeader.svelte';
	import { images } from '$lib/assets/hums/index';
	import DesignVideo from '$lib/assets/hums/WF Prototypes.mp4';
	import Outcomevideo from '$lib/assets/hums/Final sceens walkthrough.mp4';
	import { onMount } from 'svelte';

	const sections = ['title', 'context', 'field', 'analysis', 'design', 'evaluation', 'outcome'];

	let currentSection = $state(sections[0]);

	onMount(() => {
		const observer = new IntersectionObserver(
			(entries) => {
				entries.forEach((entry) => {
					if (entry.isIntersecting) {
						currentSection = entry.target.id;
					}
				});
			},
			{
				threshold: [0.1],
				rootMargin: '-50px 0px'
			}
		);

		sections.forEach((section) => {
			const element = document.getElementById(section);
			if (element) {
				observer.observe(element);
			}
		});

		return () => {
			observer.disconnect();
		};
	});
</script>

<div class="root">
	<ProjectHeader {currentSection} />
	<section class="layout-grid full-bleed" id="context">
		<img src={images['Context']} alt="" />
	</section>
	<hr />
	<section class="layout-grid full-bleed" id="field">
		<img src={images['FieldStudy']} alt="" />
	</section>
	<hr />
	<section class="layout-grid full-bleed" id="analysis">
		<img src={images['Analysis']} alt="" />
	</section>
	<hr />
	<section class="layout-grid full-bleed" id="design">
		<img src={images['Design1']} alt="" />
		<video controls>
			<source src={DesignVideo} type="video/mp4" />
			Your browser does not support the video element.
		</video>
		<img src={images['Design2']} alt="" />
	</section>
	<hr />
	<section class="layout-grid full-bleed" id="evaluation">
		<img src={images['Evaluation']} alt="" />
	</section>
	<hr />
	<section class="layout-grid full-bleed" id="outcome">
		<img src={images['Outcome1']} alt="" />
		<video controls>
			<source src={Outcomevideo} type="video/mp4" />
			Your browser does not support the video element.
		</video>
		<img src={images['Outcome2']} alt="" />
	</section>

	<footer>Thanks for viewing :)</footer>
</div>

<style>
	img {
		grid-column: 1 / -1;
	}
	video {
		grid-column: 3 / -3;
	}
	hr {
		grid-column: 3 / -1;
		color: black;
		opacity: 25%;
	}
	footer {
		width: 100%;
		padding: 4rem;

		display: flex;
		justify-content: center;
		align-items: center;

		background-color: #ffe4d6;
	}
</style>
