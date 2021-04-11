# focus-button

## Run

```bash
git clone git@github.com:lukaszpolowczyk/focus-button.git
cd focus-button
npm run dev
```

Open url: [http://localhost:3000/1]

## Problem

1. Refresh page
2. the "focused" button are focused
3. Press right arrow on keyboard
4. the "focused" button loses focus

**Question:** how to keep focus?

The code looks like this:

```svelte
<!-- src/routers/[slug].svelte -->
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
```
　
```svelte
<!-- src/routers/$layout.svelte -->
<script>
  import { onMount } from 'svelte';
  import '../app.css';
  
  let b;
  onMount(()=>b.focus());
</script>
<button bind:this={b}>focused</button>
<slot />
```
