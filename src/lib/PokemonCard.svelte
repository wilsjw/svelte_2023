<script>
    export let p;
</script>

<a href="/pokemon/{p}">
    <div class="card">
        <div class="card-image" style="background-image: url('https://img.pokemondb.net/artwork/large/{p}.jpg')"></div>
        <div class="card-info">
            <h2>{p}</h2>
        </div>
    </div>
</a>