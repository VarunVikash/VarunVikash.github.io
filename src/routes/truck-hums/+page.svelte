<script>
	import ProjectHeader from '$lib/components/ProjectHeader.svelte';
	import { images } from '$lib/assets/hums/index';
	import DesignVideo from '$lib/assets/hums/WF Prototypes.mp4';
	import Outcomevideo from '$lib/assets/hums/Final sceens walkthrough.mp4';
</script>

<ProjectHeader />
<section class="layout-grid full-bleed" id="context">
	<img src={images['Context']} alt="" />
</section>
<hr />
<section class="layout-grid full-bleed" id="field-study">
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

<style>
	img {
		grid-column: 1 / -1;
	}
	video {
		grid-column: 2 / -2;
	}
	hr {
		color: black;
		opacity: 25%;
	}
</style>
