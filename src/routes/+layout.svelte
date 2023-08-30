<script>
    import Header from '$lib/Header.svelte'
    import Footer from '$lib/Footer.svelte'
</script>

<svelte:head>
    <link rel="stylesheet" href="/css/main.css">
    <title>Pokémon</title>
</svelte:head>

<Header />
<slot />
<Footer />