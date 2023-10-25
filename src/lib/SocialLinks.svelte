<script>
    export let title;
    export let link;
    export let img;
</script>

<li id={title.toLowerCase()}>
    <img id={`${title.toLowerCase()}-icon`} alt={`${title} icon`} src={img}>
    <a href={link} target="_blank" class="fancy-underline">
        <p>{title}</p>
    </a>
</li>