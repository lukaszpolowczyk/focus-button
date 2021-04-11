<!-- src/routers/[slug].svelte -->
<svelte:head><title>Lost focus - Sveltekit Routers</title></svelte:head>
<script>
  import { page } from '$app/stores';
  
</script>
<br>
page {$page.params.slug}
