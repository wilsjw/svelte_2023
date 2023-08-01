<style>
    .background {
        height: 100%;
        width: 100.1%;
        transform: translate(-0.5%, -0.8%);
        background-image: url("images/background.jpg");
        background-repeat: no-repeat;
        background-size: contain;
        position: absolute;
    }

    .main {
        padding: 3rem 4rem;
    }

    #top h1 {
        color: pink;
        transition: ease-out .3s;
    }

    #top h1:hover {
        color: cyan;
        transition: ease-in .3s;
    }

    img#cyberpunk {
        width: 480px;
        transition: cubic-bezier(0.215, 0.610, 0.355, 1) width 0.5s;
    }

    img#cyberpunk:hover {
        width: 720px;
        transition: cubic-bezier(0.215, 0.610, 0.355, 1) width 0.5s;
    }

    img#cyberpunk {
        width: 480px;
    }

    .socials * {
        margin: 0 0 0.2rem 0.4rem;
        text-decoration: none;
        display: flex;
    }

    .socials a {
        color: red;
    }

    .socials a:visited {
        margin: 0;
        text-decoration: none;
    }

    .socials a:hover {
        color: maroon; 
    }

    .socials img {
        width: 36px;
        margin: -0.6rem 0 0 -2rem;
    }
</style>

<script>
    import Header from '$lib/Header.svelte';
</script>

<div class="background">
    <Header />
    <div class="main">
        <div id="top">
            <h1>John Wilson Best Cool Website</h1>
            <h2>only the best are welcome</h2>
    
            <p>you are not</p>

            <audio autoplay loop>
                <source src="audio/ffxiv.mp3">
            </audio>
        </div>

        <div id="centre">
            <h3>To-do:</h3>
            <ol>
                <li>become cool</li>
                <li>get money</li>
                <li>swagger</li>
            </ol>

            <h2>Welcome</h2>
            <img id="cyberpunk" alt="Favourite game right now" src="images/cyberpunk.jpg">
        </div>
        
        <div id="bottom">
            <ul class="socials">
                <li id="yt">
                    <img id="yt-icon" alt="YT icon" src="images/youtube.png">
                    <a href="https://www.youtube.com/@ashures_" target="_blank">
                        <p>YouTube</p>
                    </a>
                </li>
                <li id="twitter">
                    <img id="yt-icon" alt="YT icon" src="images/youtube.png">
                    <a href="https://www.twitter.com/ashures_" target="_blank">
                        <p>Twitter</p>
                    </a>
                </li>
                <li id="twitch">
                    <img id="yt-icon" alt="YT icon" src="images/youtube.png">
                    <a href="https://www.twitch.com/ashuress" target="_blank">
                        <p>Twitch</p>
                    </a>
                </li>
                <li id="games">
                    <img id="yt-icon" alt="YT icon" src="images/youtube.png">
                    <a href="https://ashures.w3spaces.com/" target="_blank">
                        <p>Games</p>
                    </a>
                </li>
            </ul>
        </div>
    </div>
</div>

