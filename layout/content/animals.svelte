<script>
  export let title, content, allContent;
  import Pager from '../components/pager.svelte';

  $: currentCatsPage = content.pager[0];
  let allCats = allContent.filter(content => content.type == "cats");
  let totalCats = allCats.length;
  let catsPerPage = 2;
  let totalCatPages = Math.ceil(totalCats / catsPerPage);
  $: catsRangeHigh = currentCatsPage * catsPerPage;
  $: catsRangeLow = catsRangeHigh - catsPerPage;

  $: currentDogsPage = content.pager[1];
  let allDogs = allContent.filter(content => content.type == "dogs");
  let totalDogs = allDogs.length;
  let dogsPerPage = 2;
  let totalDogPages = Math.ceil(totalDogs / dogsPerPage);
  $: dogsRangeHigh = currentDogsPage * dogsPerPage;
  $: dogsRangeLow = dogsRangeHigh - dogsPerPage;
</script>

<h1>{title}</h1>

<h3>Cats</h3>
<table>
  <thead>
    <td>Name</td>
    <td>Weight</td>
    <td>Color</td>
    <td>Outdoor</td>
  </thead>
  <tbody>
    {#each allCats as cat, i}
      {#if i >= catsRangeLow && i < catsRangeHigh}
        <tr>
          <td>{cat.fields.name}</td>
          <td>{cat.fields.weight}</td>
          <td>{cat.fields.color}</td>
          <td>{cat.fields.outdoor}</td>
        </tr>
      {/if}
    {/each}
  </tbody>
</table>

<Pager currentPage={currentCatsPage} totalPages={totalCatPages} />

<h3>Dogs</h3>
<table>
  <thead>
    <td>Name</td>
    <td>Weight</td>
    <td>Color</td>
    <td>Outdoor</td>
  </thead>
  <tbody>
    {#each allDogs as dog, i}
      {#if i >= dogsRangeLow && i < dogsRangeHigh}
        <tr>
          <td>{dog.fields.name}</td>
          <td>{dog.fields.weight}</td>
          <td>{dog.fields.color}</td>
          <td>{dog.fields.outdoor}</td>
        </tr>
      {/if}
    {/each}
  </tbody>
</table>

<Pager currentPage={currentDogsPage} totalPages={totalDogPages} />

<a href="/">Home</a>
