<script>
	import '$lib/styles/global.css';
	import '$lib/styles/utils.css';
	import '$lib/styles/normalize.css';
	import Header from '$lib/components/Header.svelte';
	import Footer from '$lib/components/Footer.svelte';

</script>
<Header />
<main>
	<slot />
</main>
<Footer />