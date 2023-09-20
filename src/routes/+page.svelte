<script>
    import { onMount } from "svelte";
    import PokemonList from "$lib/PokemonList.svelte";

    let pokemon = [];
    let currentUrl = "https://pokeapi.co/api/v2/pokemon?limit=30";
    let prevUrl = "";
    let nextUrl = "";
    let totalPokemon = 0;

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

    onMount(async () => {
        scrollPokeball();

        await updatePokemon(currentUrl);
    });

    function scrollPokeball() {
        const pokeball = document.getElementById('pokeball');
        const scroll = window.scrollY;

        pokeball.style.transform = `rotate(${360 * scroll / window.innerHeight}deg)`;

        requestAnimationFrame(scrollPokeball);
    }

    
</script>

<div class="main">
    <div id="top">
        <div id="index-title">
            <h1>Pokémon</h1>
        </div>
        <div id="pokeball">
            <img alt="pokeball" src="images/pokeball.svg">
        </div>
    </div>

    <div id="centre">
        <h2 id="pokemon-title">All Pokémon. Ever.</h2>
        <div id="change-pokemon">
            <button on:click={() => updatePokemon(prevUrl)} id="prev-pokemon">{"<"}</button>
            <button on:click={() => updatePokemon(nextUrl)} id="next-pokemon">{">"}</button>
        </div>
        <PokemonList pokemon={pokemon} />
    </div>
    
    <div id="bottom">
        
    </div>
</div>
