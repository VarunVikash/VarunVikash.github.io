<script lang="ts">
	import { images } from '$lib/assets/projects/index';

	let {
		title,
		description,
		tags,
		featured = false,
		color,
		image,
		url,
		childImage
	} = $props<{
		title: string;
		description: string;
		tags: string[];
		featured?: boolean;
		color: string;
		image: string;
		url: string;
		childImage?: string;
	}>();
</script>

<a href={url} target={url.includes('http') ? '_blank' : '_self'}>
	<article
		class:featured
		style:background-image={`linear-gradient(to right, ${color}, transparent), url('${images[image]}')`}
	>
		<div class="main-content">
			<h3>{title}</h3>
			<p>{description}</p>
		</div>

		<ul class="tags">
			{#each tags as tag, index}
				<li>{tag}</li>
				{#if index !== tags.length - 1}&nbsp;|&nbsp;{/if}
			{/each}
		</ul>

		{#if childImage}
			<img src={images[childImage]} alt={childImage} class="child-image" />
		{/if}
	</article>
</a>

<style>
	a {
		display: contents;
	}
	article {
		position: relative;

		height: 30dvh;

		grid-column: 3 / span 8;

		display: flex;
		flex-direction: column;
		justify-content: space-between;
		padding: 1.5rem;

		border-radius: 1rem;

		background-size: cover;
		background-position: center;

		color: white;

		&.featured {
			height: 50dvh;
		}

		box-shadow: 0px 10px 15px -3px rgba(0, 0, 0, 0.1);

		&:hover h3 {
			text-decoration: underline;
			text-underline-offset: 0.25rem;
		}
	}
	.main-content {
		width: 50%;

		display: flex;
		flex-direction: column;
		gap: 0.5rem;

		& * {
			text-wrap: balance;
			text-wrap: pretty;
		}
	}
	h3 {
		font-size: 1.75rem;
		font-weight: 700;
	}
	ul {
		display: flex;
	}
	.child-image {
		position: absolute;
		right: 0;
		top: 0;
		height: 100%;

		padding: 1.5rem;

		object-fit: cover;
	}
</style>
