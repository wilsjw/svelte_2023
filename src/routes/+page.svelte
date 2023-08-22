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
        fetch(currentUrl)
        .then(response => response.json())
        .then(data => {
            pokemon = data.results.map(p => p.name);
            nextUrl = data.next;
            prevUrl = data.previous;
            totalPokemon = data.count;
        })
        .catch(error => console.log(error));
    });

    function imageClick(event) {
        let targetImgElement = document.getElementById(event.srcElement.id);
        let overlay = document.getElementById("image-overlay");

        focusImage = targetImgElement.src;
        focusTitle = targetImgElement.id;
        overlay.style.display = "block";

        console.log(event);
        
    }

    function closeOverlay() {
        let overlay = document.getElementById("image-overlay");

        overlay.style.display = "none";
    }

    async function updatePokemon(urlToUse) {
        fetch(urlToUse)
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
        <div id="image-overlay">
            <div id="main">
                <img src={focusImage} alt="" id="focus-image">
                <p id="focus-title">{focusTitle}</p>
            </div>
            <button on:click={closeOverlay} id="close-button">X</button>
        </div>

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
