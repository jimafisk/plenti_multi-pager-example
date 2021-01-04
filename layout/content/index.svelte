<script>
	export let title, body;
</script>

<h1>{title}</h1>

{#each body as p}
  <p>{@html p}</p>
{/each}
