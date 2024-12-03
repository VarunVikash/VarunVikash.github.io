<script>
	import headerImage from '$lib/assets/profile.png';
</script>

<header class="layout-grid full-bleed">
	<div class="content">
		<h1>Hi, I'm Varun</h1>
		<p>
			I’m an interaction designer and researcher with a rationale-driven thought process and clear
			articulation skills
		</p>
	</div>
	<div
		class="image"
		style:background-image={`linear-gradient(to right, black 0%, transparent 60%), url(${headerImage})`}
	></div>
</header>

<style>
	header {
		height: 60dvh;
		width: 100dvw;

		padding-inline-start: 4rem;
		align-items: center;

		background-color: black;
		color: white;
	}
	.content {
		grid-column: 1 / span 3;
		display: flex;
		flex-direction: column;
		gap: 1rem;
		transform: translateY(-2rem);

		& * {
			text-wrap: balance;
			text-wrap: pretty;
		}
	}
	h1 {
		font-size: 2.5rem;
		font-weight: 600;
	}
	.image {
		grid-column: 8 / -1;
		width: 100%;
		height: 60dvh;
		background-position: center;
		background-size: cover;
	}
</style>
