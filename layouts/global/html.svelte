<script>
  import Head from './head.svelte';

  export let layout, content, allContent;
</script>

<html lang="en">
<Head title={content.filename} />
<body>
  <svelte:component this={layout} {...content.fields} {content} {allContent} />
</body>
</html>
