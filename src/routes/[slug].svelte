<!-- [slug].svelte -->
<svelte:head><title>Lost focus - Sveltekit Routers</title></svelte:head>
<script>
	import { page } from '$app/stores';
	import { goto } from '$app/navigation';
		
  import Keydown from "svelte-keydown";
</script>
<Keydown on:ArrowRight={() => goto(`${Number($page.params.slug)+1}`) } />
<br>
<button on:click={()=>goto(`${Number($page.params.slug)+1}`)}>goto({Number($page.params.slug)+1})</button>
or press RightArrow

