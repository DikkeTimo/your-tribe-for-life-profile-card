<script>
  import { SliceZone } from '@prismicio/svelte'
  import { components } from '$lib/slices' 
  export let data
  console.log(data)

  /** @type {import("@prismicio/client").Content.NamePfSlice} */

</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>


<section>
  <SliceZone slices={data.slices} {components} />
</section>