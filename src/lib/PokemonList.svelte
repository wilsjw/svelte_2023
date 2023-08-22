<script>
    export let pokemon;
    let spriteUrl = "https://img.pokemondb.net/artwork/large/"
    let spriteFileType = ".jpg"
</script>

<div class="pokemon-grid">
    {#each pokemon as poke}
        <img src={spriteUrl + poke + spriteFileType} alt={poke}>
    {/each}
</div>