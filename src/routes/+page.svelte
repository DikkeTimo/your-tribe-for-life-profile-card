<script>
  import { SliceZone } from "@prismicio/svelte";
  import { components } from "$lib/slices";
  export let data;
  // /** @type {import("@prismicio/client").Content.NamePfSlice} */

  import { PrismicImage } from '@prismicio/svelte'
</script>

<SliceZone slices={data.document} {components} />



<!-- 
<h1>{data.slices[0].primary.name[0].text}</h1>
<h2>{data.slices[0].primary.lastename[0].text}</h2> -->

<!-- {#each data.slices as slice}
  {#each slice.primary.name as item}
    <p>{item.text}</p>
  {/each}
{/each} -->


<div class="card">
  <div class="personal_info">
    <div class="picture">
      <img src= {data.slices[0].primary.timpf.url} alt="Image Alt Text" />
    </div>
    <div class="name">
      <h1>{data.slices[0].primary.name[0].text} {data.slices[0].primary.lastename[0].text} </h1>
    </div>
    <div class="socials"></div>
  </div>
  <div class="about_info"></div>
</div>

<style>

  :global(*) {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  :global(body) {
    background-color: var(--backgroundcolor);
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100vh;
  }

  :global(:root) {
    --backgroundcolor: #09A9D1;
    --maincolor: #444444;
    --textcolor: #fff;

    --borderr: 30px;
  }
  .card {
    background-color: var(--maincolor);
    color: var(--textcolor);
    border-radius: var(--borderr);
    width: 85vw;
    height: 80vh;
  }

  .personal_info {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    width: 20vw;
    height: 100%;
  }




  .picture img {
    width: 100%;
    border-radius: 50%;
    border: 3px solid var(--textcolor);
  }


</style>
