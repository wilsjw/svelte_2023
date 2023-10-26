<script>
    import { onMount } from "svelte";
    import getAPI from "$lib/utils/getAPI.js";
    import PokemonList from "$lib/components/PokemonList.svelte";

    let pokemon = [];
    let currentUrl = "https://pokeapi.co/api/v2/pokemon?limit=30";
    let prevUrl = "";
    let nextUrl = "";
    let totalPokemon = 0;

    const updatePokemon = async (url) => {
        
        const data = await getAPI(url);

        pokemon = data.results.map(p => p.name);
        nextUrl = data.next;
        prevUrl = data.previous;
        totalPokemon = data.count;
        
        /* Old fetch, new is easier to read and manipulate */
        // await fetch(urlToUse)
        //     .then(response => response.json())
        //     .then(data => {
        //         pokemon = data.results.map(p => p.name);
        //         nextUrl = data.next;
        //         prevUrl = data.previous;
        //         totalPokemon = data.count;
        //     })
        //     .catch(error => console.log(error));
    }

    onMount(async () => {
        scrollPokeball();

        await updatePokemon(currentUrl);
    });

    // Rotates a Pokeball on the landing page by the scroll amount
    const scrollPokeball = () => {
        const pokeball = document.getElementById('pokeball');
        const scroll = window.scrollY;

        pokeball.style.transform = `rotate(${360 * scroll / window.innerHeight}deg)`;

        // Requests the browser to run this whenever there is enough spare resources available instead of slowing down the site
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
        <!-- Allows page changing using the URLs obtained in the previous fetch to update the Pokemon -->
        <div id="change-pokemon">
            <button on:click={() => updatePokemon(prevUrl)} id="prev-pokemon">{"<"}</button>
            <button on:click={() => updatePokemon(nextUrl)} id="next-pokemon">{">"}</button>
        </div>
        <PokemonList pokemon={pokemon} />
    </div>
    
    <div id="bottom">
        
    </div>
</div>
