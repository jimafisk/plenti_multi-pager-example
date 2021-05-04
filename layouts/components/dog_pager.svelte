<script>
  export let currentCatsPage, currentDogsPage, totalCatPages, totalDogPages;
</script>

<ul>
  {#if currentDogsPage > 1}
    <li><a href="/animals/cats/{currentCatsPage}/dogs/1">first</a></li>
    <li><a href="/animals/cats/{currentCatsPage}/dogs/{currentDogsPage - 1}">prev</a></li>
  {:else}
    <li><span>first</span></li>
    <li><span>prev</span></li>
  {/if}
  {#each [3,2,1] as i}
    {#if currentDogsPage - i > 0}
      <li><a href="/animals/cats/{currentCatsPage}/dogs/{currentDogsPage - i}">{currentDogsPage - i}</a></li>
    {/if}
  {/each}
  <li><span>{currentDogsPage}</span></li>
  {#each Array(3) as _, i}
    {#if currentDogsPage + (i+1) <= totalDogPages}
      <li><a href="/animals/cats/{currentCatsPage}/dogs/{currentDogsPage + (i+1)}">{currentDogsPage + (i+1)}</a></li>
    {/if}
  {/each}
  {#if currentDogsPage < totalDogPages}
    <li><a href="/animals/cats/{currentCatsPage}/dogs/{currentDogsPage + 1}">next</a></li>
    <li><a href="/animals/cats/{currentCatsPage}/dogs/{totalDogPages}">last</a></li>
  {:else}
    <li><span>next</span></li>
    <li><span>last</span></li>
  {/if}
</ul>

<style>
  ul {
    display: flex;
    max-width: 600px;
    margin: 20px auto;
  }
  li {
    flex-grow: 1;
    list-style: none;
  }
  a {
    text-align: center;
    padding: 5px 20px;
    border-radius: 5px;
    background: #f0efef;
  }
  span {
    text-align: center;
    padding: 5px 20px;
    color: gray;
  }
</style>
