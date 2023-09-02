<script>
    export let pokemon;

    let spriteUrl = "https://img.pokemondb.net/artwork/large/"
</script>

<div class="pokemon-grid">
    {#each pokemon as p}
        <a href="/pokemon/{p}">
            <div class="card">
                <div class="card-image" style={"background-image: url('" + spriteUrl + p + ".jpg')"}></div>
                <div class="card-info">
                    <h2>{p}</h2>
                </div>
            </div>
        </a>
    {/each}
</div>