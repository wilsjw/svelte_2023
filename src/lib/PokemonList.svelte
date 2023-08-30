<script>
    export let pokemon;

    let spriteUrl = "https://img.pokemondb.net/artwork/large/"
    let spriteFileType = ".jpg"
</script>

<div class="pokemon-grid">
    {#each pokemon as p}
        <div class="card">
            <a href={`/pokemon/${p}`}>
                <img src={spriteUrl + p + spriteFileType} alt={p} id={p}>
            </a>
        </div>
    {/each}
</div>