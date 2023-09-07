<script>
  import { SliceZone } from "@prismicio/svelte";
  import { components } from "$lib/slices";
  export let data;
  // /** @type {import("@prismicio/client").Content.NamePfSlice} */

  import { PrismicImage } from '@prismicio/svelte'
</script>

<SliceZone slices={data.document} {components} />


<img src={data.slices[0].primary.timpf.url} alt="Image Alt Text" />

<!-- 
<h1>{data.slices[0].primary.name[0].text}</h1>
<h2>{data.slices[0].primary.lastename[0].text}</h2> -->

{#each data.slices as slice}
  {#each slice.primary.name as item}
    <p>{item.text}</p>
  {/each}
{/each}


<div class="card">
  <div class="personal_info"></div>
  <div class="about_info"></div>
</div>

<style>

  :global(*) {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  :global(body) {
    width: 100%;
    height: 100vh;
  }
  .card {
    background-color: aqua;
    width: 80vw;
    height: 75vh;
  }
</style>
