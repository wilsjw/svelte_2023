<script>
    import { page } from '$app/stores'
    import { onMount } from 'svelte';

    let loading = true;

    let pokemon = {};
    let types = [];
    let abilities = [];
    let sprites = {};
    let stats = [];
    let moves = [];

    // Run once the page has connected to the browser
    onMount(async () => {
        // The following code requests information from the PokeAPI website using the pokemon name/id as the query. 
        // This is taken from the page parameters that the user can type manually or from the Pokemon cards.
        try {
            const res = await fetch(`https://pokeapi.co/api/v2/pokemon/${$page.params.id}/`);
            const data = await res.json();

            pokemon = data;
            types = data.types;
            abilities = data.abilities;
            sprites = data.sprites;
            stats = data.stats;
            moves = data.moves;
        } catch (error) {
            console.log(error);
        }
        
        loading = false;

        // await fetch(`https://pokeapi.co/api/v2/pokemon/${$page.params.id}/`)
        // .then(res => res.json())
        // .then(data => {
        //     pokemon = data;
        //     types = data.types.map(t => t);
        //     abilities = data.abilities.map(a => a);
        //     sprites = data.sprites;
        //     stats = data.stats.map(s => s);
        //     moves = data.moves.map(m => m);
        // }).catch(error => {
        //     console.log(error);
        // });
    });
</script>

<!-- 
    Using the loading variable, waits for the fetch call above to return potential data.
    Whilst the data is loading, a loading symbol is displayed to show the user the page is still working
-->
{#if loading}
    <div id="loading-pokemon">
        <div class="loading-poke-content">
            <h1 id="loading-header">Loading...</h1>
        </div>
    </div>
{:else}
    <div class="pokemon-page-main">
        {#if JSON.stringify(pokemon) !== '{}'}
            <!-- If the data exists it is displayed using the HTML beneath -->
            <div class="pokemon-page-info">
                <img src={sprites.front_default} alt={pokemon.name}>
                <div class="pokemon-page-info-text">
                    <h1>{pokemon.id < 10 ? `0${pokemon.id}` : pokemon.id} - {pokemon.name}</h1>
                    <p><b>types: </b>{#each types as t}<span class={`pokemon-type type-${t.type.name}`}>{t.type.name} </span>{/each}</p>
                    
                    <p><b>abilities:</b></p>
                    <ul>
                        {#each abilities as a}
                            <li>{a.ability.name} <b>{a.is_hidden ? " - hidden"  : ""}</b></li>
                        {/each}
                    </ul>
                    <p><b>height:</b> {pokemon.height / 10}m <b>weight:</b> {pokemon.weight / 10}kg</p>
                </div>
            </div>
            <div class="pokemon-page-stats">
                <h2>stats</h2>
                {#each stats as s}
                    <p><b>{s.stat.name}:</b> {s.base_stat}</p>
                {/each}
            </div>
            <div class="pokemon-page-moves">
                <h2>moves</h2>
                <div class="pokemon-move-list">
                    {#each moves as m}
                        <div class="pokemon-move">
                            {m.move.name}
                        </div>
                    {/each}
                </div>
            </div>
            {:else}
            <div class="pokemon-missing">
                <h1>Sorry!</h1>
                <h2>There is no information for this pokemon.</h2>
            </div>
        {/if}
    </div>
{/if}


