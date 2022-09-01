<script>
  import Personaje from './libs/Character.svelte'
  let characteres = [];
  let page = 1;

  const loadCharacter = async () => {
    const res = await fetch(
      "https://rickandmortyapi.com/api/character?page=" + page
    );
    const data = await res.json();
    characteres = data.results;
  };
  loadCharacter();


  const nextPage = () => {
    page++
    loadCharacter()    
   };
  const previousPage = () => {
    page--;
    loadCharacter()
  };
</script>

<main>
  <h1 class="title">Rick And Morty With Svelte</h1>
  
  <div  class="container">
    <div class="btns"> 
      <button class="btn" disabled={page === 1} on:click={previousPage}>Previous</button>
      <button class="btn" on:click={nextPage}>Next</button>
    </div>
   <div class="grid">
    {#each characteres as c}
    <Personaje c={c}/>
      
    {/each}

   </div>
  </div>
</main>

<style>
</style>
