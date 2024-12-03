<script lang="ts">
	import '$lib/styles/reset.css';
	import '$lib/styles/global.css';

	let { children } = $props();
</script>

<script:head>
	<link rel="preconnect" href="https://rsms.me/" />
	<link rel="stylesheet" href="https://rsms.me/inter/inter.css" />
</script:head>

{@render children()}
