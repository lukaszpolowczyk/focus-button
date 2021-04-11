<script>
  import { onMount } from 'svelte';
	import '../app.css';
	
	let b;
	onMount(()=>b.focus());
</script>
<button bind:this={b}>focused</button>
<slot />

