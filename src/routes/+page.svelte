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
            pokemon = data.results;
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
        <PokemonList />
    </div>
    
    <div id="bottom">
        
    </div>
</div>
