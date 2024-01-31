<script>
	import Home from './Home.svelte';
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcome_fallback from '$lib/images/svelte-welcome.png';
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="tech-interview" />
</svelte:head>

<section class="content-area">
	<div class="background">
		<Home />
		<!-- <Page1/> -->
	</div>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}

	.content-area {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	/* .background{
		border: solid;
	} */
</style>