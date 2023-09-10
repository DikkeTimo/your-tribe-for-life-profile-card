<script>
  import { SliceZone } from "@prismicio/svelte";
  import { components } from "$lib/slices";
  export let data;
  // /** @type {import("@prismicio/client").Content.NamePfSlice} */

  import { PrismicImage } from "@prismicio/svelte";
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
      <img src={data.slices[0].primary.timpf.url} alt="Image Alt Text" />
    </div>
    <div class="name">
      <h1>
        {data.slices[0].primary.name[0].text}
        {data.slices[0].primary.lastename[0].text}
      </h1>
      <p>Frontend developer</p>
    </div>
    <div class="socials" />
  </div>
  <div class="info">
    <div class="about_me">
      <div class="story">
        <h3>About <span>Me</span></h3>
        <p>{data.slices[0].primary.about}</p>
      </div>
      <div class="age">
        <p>Age <span /></p>
      </div>
    </div>
  </div>
</div>

<!-- <pre>
	{JSON.stringify(data, null, 2)}
</pre> -->

<style>
  :global(*) {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    font-family: "Golos Text", sans-serif;
    font-family: "Poppins", sans-serif;
  }

  :global(body) {
    background-color: var(--backgroundcolor);
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100vh;
    line-height: 1.7;
  }
  :global(:root) {
    --backgroundcolor: #09a9d1;
    --maincolor: #444444;
    --maincolor2: #222222;
    --textcolor: #fff;
    --textcolor2: #06b4e0;

    --borderr: 30px;
    --fontsize: 30px;
  }
  .card {
    display: flex;
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
    width: 35vw;
    height: 100%;

    & .name p {
      opacity: 0.7;
      text-align: center;
    }

    & .picture img {
      width: 100%;
      border-radius: 50%;
      border: 3px solid var(--textcolor);
    }
  }

  .info {
    background-color: var(--maincolor2);
    border-radius: var(--borderr);
    width: 100%;
    padding: 5rem;
    overflow-y: scroll;

    & .about_me {
      display: flex;
      justify-content: space-between;
    }

    & .story {
      width: 20vw;
      & h3 {
        font-size: var(--fontsize);
      }
      & span {
        color: var(--textcolor2);
      }
      & p {
        margin-top: 4rem;
      }
    }

    & .age {
      width: 20vw;
    }
  }
</style>

