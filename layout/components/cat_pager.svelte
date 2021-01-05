<script>
  export let currentCatsPage, currentDogsPage, totalCatPages, totalDogPages;
</script>

<ul>
  {#if currentCatsPage > 1}
    <li><a href="/animals/cats/1/dogs/{currentDogsPage}">first</a></li>
    <li><a href="/animals/cats/{currentCatsPage - 1}/dogs/{currentDogsPage}">prev</a></li>
  {:else}
    <li><span>first</span></li>
    <li><span>prev</span></li>
  {/if}
  {#each [3,2,1] as i}
    {#if currentCatsPage - i > 0}
      <li><a href="/animals/cats/{currentCatsPage - i}/dogs/{currentDogsPage}">{currentCatsPage - i}</a></li>
    {/if}
  {/each}
  <li><span>{currentCatsPage}</span></li>
  {#each Array(3) as _, i}
    {#if currentCatsPage + (i+1) <= totalCatPages}
      <li><a href="/animals/cats/{currentCatsPage + (i+1)}/dogs/{currentDogsPage}">{currentCatsPage + (i+1)}</a></li>
    {/if}
  {/each}
  {#if currentCatsPage < totalCatPages}
    <li><a href="/animals/cats/{currentCatsPage + 1}/dogs/{currentDogsPage}">next</a></li>
    <li><a href="/animals/cats/{totalCatPages}/dogs/{currentDogsPage}">last</a></li>
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
