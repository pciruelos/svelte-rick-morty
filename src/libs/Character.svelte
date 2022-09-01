<script>
    export let c
</script>

<div class="character"> 
    <img src={c.image} alt={c.name} />
    <h2 class="charactertitle">{c.name}</h2>
    <h3 class="charactertitle h3title">{c.species}</h3>
</div>