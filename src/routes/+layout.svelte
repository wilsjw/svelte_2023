<script>
    import Header from '$lib/components/Header.svelte'
    import Footer from '$lib/components/Footer.svelte'
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