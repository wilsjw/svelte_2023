<script>
    import { onMount } from "svelte";
    import PokemonList from "../lib/PokemonList.svelte";

    let focusImage = "images/home/mew.jpg";
    let focusTitle = "mew";

    let pokemon = [];
    let currentUrl = "https://pokeapi.co/api/v2/pokemon";
    let prevUrl = "";
    let nextUrl = "";
    let totalPokemon = 0;

    onMount(async () => {
        await fetch(currentUrl)
        .then(response => response.json())
        .then(data => {
            pokemon = data.results.map(p => p.name);
            nextUrl = data.next;
            prevUrl = data.previous;
            totalPokemon = data.count;
        })
        .catch(error => console.log(error));
    });

    async function updatePokemon(urlToUse) {
        await fetch(urlToUse)
            .then(response => response.json())
            .then(data => {
                pokemon = data.results.map(p => p.name);
                nextUrl = data.next;
                prevUrl = data.previous;
                totalPokemon = data.count;
            })
            .catch(error => console.log(error));
    }
</script>

<div class="main">
    <div id="top">
        <div id="index-title">
            <h1>Pokémon</h1>
        </div>
    </div>

    <div id="centre">
        <h2>All Pokémon. Ever.</h2>
        <div id="change-pokemon">
            <button on:click={() => updatePokemon(prevUrl)} id="prev-pokemon">{"<"}</button>
            <button on:click={() => updatePokemon(nextUrl)} id="next-pokemon">{">"}</button>
        </div>
        <PokemonList pokemon={pokemon} />
    </div>
    
    <div id="bottom">
        
    </div>
</div>
