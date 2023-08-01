<script>
    import Header from '$lib/Header.svelte';
    import Footer from '$lib/Footer.svelte';
</script>

<svelte:head>
    <link rel="stylesheet" href="css/main.css">
    <title>John Wilson Best Cool Website</title>
</svelte:head>

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
            <Footer />
        </div>
    </div>
</div>

