<script>
	import Navbar from '$lib/components/Navbar.svelte';
	import Header from '$lib/components/Header.svelte';
	import Footer from '$lib/components/Footer.svelte';
	import ProjectCard from '$lib/components/ProjectCard.svelte';

	const projects = [
		{
			title: 'Truck HUMS',
			description:
				'Field study, Design & Evaluation of smartphone interface for condition monitoring and predictive maintenance of trucks for small-scale truck owners (owning <5 trucks) in India',
			tags: ['UX Research', 'UX Design'],
			color: '#DC7945',
			featured: true,
			image: 'Truck',
			childImage: 'TruckApp',
			url: '/truck-hums'
		},
		{
			title: 'Augsburger 101',
			description:
				'Location-based mobile tour guide app using Augmented Reality for exploration of cultural heritage through playful interactions',
			tags: ['UX Design for AR'],
			color: '#A7A3A7',
			image: 'Augs',
			url: 'https://games.hs-augsburg.de/Augsburger101/'
		},
		{
			title: 'ShareSpace',
			description:
				'Conceptualization of a mobile-based service to promote collaborative e-commerce based on shared economy and design of the interface for it',
			tags: ['UX Design', 'Service Design'],
			color: '#00737C',
			image: 'ShareSpace',
			url: 'https://www.behance.net/gallery/76921627/Co-owning-Renting-Platform'
		},
		{
			title: 'Faze',
			description:
				'An exploration and prototyping the use of gaze input and facial gestures for desktop control (tab & window switching)',
			tags: ['Human-Computer Interaction'],
			color: '#50AA73',
			image: 'Faze',
			url: 'https://cuboid-cephalopod-500.notion.site/Gaze-Facial-gestures-for-desktop-control-1509ba2e08a881f3a9e1c61b12d7d98a'
		},
		{
			title: 'Lab evaluation of tourist map',
			description:
				'Comparison of think-out-loud and retrospective think-out-loud with eye tracking as methods to evaluate variations of a tourist map',
			tags: ['UX Research'],
			color: '#37BBA6',
			image: 'MapTest',
			url: 'https://drive.google.com/file/d/16X1NICw1YnXGIhVqx_qcR-QF2-lr-a1v/view'
		},
		{
			title: 'Cognitive biases in surveys',
			description:
				'Incorporated positive and negative biases respectively to two versions of the same survey and measured influence on results',
			tags: ['UX Research'],
			color: '#D16252',
			image: 'Survey',
			url: 'https://drive.google.com/file/d/1Qeyt2ddnPzDYAJgVLMxNiS-AO9BUdYta/view'
		}
	];
</script>

<Navbar />
<Header />
<section id="work" class="works layout-grid">
	<h2>Work</h2>
	{#each projects as project}
		<ProjectCard
			title={project.title}
			description={project.description}
			tags={project.tags}
			featured={project.featured}
			color={project.color}
			image={project.image}
			childImage={project.childImage}
			url={project.url}
		/>
	{/each}
</section>
<Footer />

<style>
	.works {
		margin-bottom: 4rem;

		gap: 2rem;
	}
	h2 {
		grid-column: 1/-1;

		font-size: 1.5rem;
		text-align: center;
		text-transform: uppercase;
		letter-spacing: 50%;

		margin-block: 4rem 2rem;
	}
</style>
