<script>
    /** @type {import('./$types').PageData} */
    export let data;
</script>

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
        padding: 0 1rem;
    }

    h1 {
        color: maroon;
    }

    img#cyberpunk {
        width: 480px;
        transition: ease-out width 0.5s;
    }

    img#cyberpunk:hover {
        width: 720px;
        transition: ease-in width 0.5s;
    }

    img#cyberpunk {
        width: 480px;
    }

    .socials * {
        margin: 0 0 0.2rem 0.4rem;
        text-decoration: none;
        display: flex;
    }

    .socials a:visited {
        margin: 0;
        text-decoration: none;
    }

    .socials img {
        width: 36px;
        margin: -0.6rem 0 0 -2rem;
    }
</style>

<div class="background">
    <div class="main">
        <h1>John Wilson Best Cool Website</h1>
        <h2>only the best are welcome</h2>

        <p>you are not</p>

        <br>
        <hr>

        <h3>To-do:</h3>
        <ol>
            <li>become cool</li>
            <li>get money</li>
            <li>swagger</li>
        </ol>

        <br>
        <hr>

        <h2>Welcome</h2>
        <img id="cyberpunk" alt="Favourite game right now" src="images/cyberpunk.jpg">

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

