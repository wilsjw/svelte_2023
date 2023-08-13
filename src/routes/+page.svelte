<script>
    let focusImage = "images/home/mew.jpg";
    let focusTitle = "mew";

    function imageClick(event) {
        let targetImgElement = document.getElementById(event.srcElement.id);
        let overlay = document.getElementById("image-overlay");

        focusImage = targetImgElement.src;
        focusTitle = targetImgElement.id;
        overlay.style.display = "block";

        // focusImageElement.src = targetImgElement.src;
        
    };

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
        <table>
            <tr>
                <th><img on:click={event => imageClick(event)} src="images/home/abra.jpg" alt="abra" id="abra" class="clickable"></th>
                <th><img on:click={event => imageClick(event)} src="images/home/bulbasaur.jpg" alt="bulbasaur" id="bulbasaur" class="clickable"></th>
                <th><img on:click={event => imageClick(event)} src="images/home/caterpie.jpg" alt="caterpie" id="caterpie" class="clickable"></th>
                <th><img on:click={event => imageClick(event)} src="images/home/charmander.jpg" alt="charmander" id="charmander" class="clickable"></th>
            </tr>
            <tr>
                <th><img on:click={event => imageClick(event)} src="images/home/cubone.jpg" alt="cubone" id="cubone" class="clickable"></th>
                <th><img on:click={event => imageClick(event)} src="images/home/dratini.jpg" alt="dratini" id="dratini" class="clickable"></th>
                <th><img on:click={event => imageClick(event)} src="images/home/eevee.jpg" alt="eevee" id="eevee" class="clickable"></th>
                <th><img on:click={event => imageClick(event)} src="images/home/geodude.jpg" alt="geodude" id="geodude" class="clickable"></th>
            </tr>
            <tr>
                <th><img on:click={event => imageClick(event)} src="images/home/grimer.jpg" alt="grimer" id="grimer" class="clickable"></th>
                <th><img on:click={event => imageClick(event)} src="images/home/jigglypuff.jpg" alt="jigglypuff" id="jigglypuff" class="clickable"></th>
                <th><img on:click={event => imageClick(event)} src="images/home/machop.jpg" alt="machop" id="machop" class="clickable"></th>
                <th><img on:click={event => imageClick(event)} src="images/home/magnemite.jpg" alt="magnemite" id="magnemite" class="clickable"></th>
            </tr>
            <tr>
                <th><img on:click={event => imageClick(event)} src="images/home/mew.jpg" alt="mew" id="mew" class="clickable"></th>
                <th><img on:click={event => imageClick(event)} src="images/home/paras.jpg" alt="paras" id="paras" class="clickable"></th>
                <th><img on:click={event => imageClick(event)} src="images/home/pidgey.jpg" alt="pidgey" id="pidgey" class="clickable"></th>
                <th><img on:click={event => imageClick(event)} src="images/home/pikachu.jpg" alt="pikachu" id="pikachu" class="clickable"></th>
            </tr>
            <tr>
                <th><img on:click={event => imageClick(event)} src="images/home/psyduck.jpg" alt="psyduck" id="psyduck" class="clickable"></th>
                <th><img on:click={event => imageClick(event)} src="images/home/rattata.jpg" alt="rattata" id="rattata" class="clickable"></th>
                <th><img on:click={event => imageClick(event)} src="images/home/sandshrew.jpg" alt="sandshrew" id="sandshrew" class="clickable"></th>
                <th><img on:click={event => imageClick(event)} src="images/home/squirtle.jpg" alt="squirtle" id="squirtle" class="clickable"></th>
            </tr>
        </table>
    </div>
    
    <div id="bottom">
        
    </div>
</div>
