<script>
  export let title, allContent;
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
    {#each allContent.filter(content => content.type == "cats") as cat}
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
    {#each allContent.filter(content => content.type == "dogs") as dog}
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
