<script>
    export let pokemon;
    export let clickPokemon;
    let spriteUrl = "https://img.pokemondb.net/artwork/large/"
    let spriteFileType = ".jpg"
</script>

<div class="pokemon-grid">
    {#each pokemon as poke}
        <img on:click={event => clickPokemon(event)} src={spriteUrl + poke + spriteFileType} alt={poke} id={poke}>
    {/each}
</div>