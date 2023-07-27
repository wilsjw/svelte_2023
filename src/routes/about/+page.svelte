<script>
    /** @type {import('./$types').PageData} */
    export let data;
</script>

<style>
    .all-items {
        padding: 0;
        margin: 0;
    }

    .main {
        height: 100%;
        width: 100.1%;
        transform: translate(-0.5%, -1%);
        background-image: url("images/about/background.jpg");
        background-repeat: no-repeat;
        background-size: cover;
        position: absolute;
    }

    #title h1 {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -80%);
        font-size: 8rem;
        color: whitesmoke;
    }
</style>

<div class="all-items">
    <div class="main">\
        <div id="overlay">
            <div id="title">
                <h1>About Me</h1>
            </div>
        </div>
    </div>
</div>  