<script>
  export let title, allContent;

  let allCats = allContent.filter(content => content.type == "cats");
  let totalCats = allCats.length;
  let catsPerPage = 3;
  let totalCatPages = Math.ceil(totalCats / catsPerPage);

  let allDogs = allContent.filter(content => content.type == "dogs");
  let totalDogs = allDogs.length;
  let dogsPerPage = 3;
  let totalDogPages = Math.ceil(totalDogs / dogsPerPage);
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
    {#each allCats as cat}
      <tr>
        <td>{cat.fields.name}</td>
        <td>{cat.fields.weight}</td>
        <td>{cat.fields.color}</td>
        <td>{cat.fields.outdoor}</td>
      </tr>
    {/each}
  </tbody>
</table>

<h3>Dogs</h3>
<table>
  <thead>
    <td>Name</td>
    <td>Weight</td>
    <td>Color</td>
    <td>Outdoor</td>
  </thead>
  <tbody>
    {#each allDogs as dog}
      <tr>
        <td>{dog.fields.name}</td>
        <td>{dog.fields.weight}</td>
        <td>{dog.fields.color}</td>
        <td>{dog.fields.outdoor}</td>
      </tr>
    {/each}
  </tbody>
</table>

<a href="/">Home</a>
