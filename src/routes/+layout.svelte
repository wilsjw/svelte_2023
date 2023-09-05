<script>
    import Header from '$lib/Header.svelte'
    import Footer from '$lib/Footer.svelte'
</script>

<svelte:head>
    <link rel="stylesheet" href="/css/main.css">
    <link rel="stylesheet" href="/css/all.css">
    <link rel="stylesheet" href="/css/types.css">
    <title>Pokémon</title>
</svelte:head>

<Header />
<slot />
<Footer />