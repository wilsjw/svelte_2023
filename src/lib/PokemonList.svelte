<script>
    import PokemonCard from "./PokemonCard.svelte";

    export let pokemon;

    let spriteUrl = "https://img.pokemondb.net/artwork/large/"
</script>

<div class="pokemon-grid">
    {#each pokemon as p}
        <PokemonCard p={p} />
    {/each}
</div>