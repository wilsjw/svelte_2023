<script>
    import { page } from '$app/stores';
    import Header from '$lib/Nav.svelte';
</script>

<style>
    #background {
        height: 100.2%;
        width: 100.6%;
        background-image: url("images/error/background.jpg");
        background-repeat: no-repeat;
        background-size: cover;
        position: absolute;
        transform: translate(-1%, -1%);
    }
</style>

<div id="background">
    <Header />
</div>