<script>
  import { SliceZone } from "@prismicio/svelte";
  import { components } from "$lib/slices";
  import { PrismicImage } from "@prismicio/svelte";
  import {fade, fly, blur, scale} from 'svelte/transition'
  
  import {onMount} from 'svelte'
  
  export let data;

  let showing = false 

  onMount(() => {
    showing = true
  });


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

{#if showing}
<div class="card">
  <div class="personal_info">
    <div class="picture">
      <img transition:fade={{ duration: 1000 }} src={data.slices[0].primary.timpf.url} alt="Image Alt Text" />
    </div>
    <div class="name">
      <h1 transition:scale={{ duration: 1000, delay: 500, opacity: 0, start: 0.5 }}>
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
        <h3 transition:fade={{ delay: 250, duration: 300, axis: 'x' }}>About <span>Me</span></h3>
        <p transition:fade={{ delay: 1500, duration: 1000 }}>{data.slices[0].primary.about}</p>
      </div>
      <div class="story">
        <h3 transition:fade={{ delay: 250, duration: 300, axis: 'x' }}>Contact <span>Me</span></h3>
        <ul>
          <li transition:fade={{ delay: 250, duration: 500, axis: 'x' }}>Tim Oosterveer</li>
          <li transition:fade={{ delay: 550, duration: 500, axis: 'x' }}>23</li>
          <li transition:fade={{ delay: 750, duration: 500, axis: 'x' }}>Lisserbroek</li>
          <li transition:fade={{ delay: 950, duration: 500, axis: 'x' }}><a href="https://github.com/DikkeTimo" target="_blank">Github</a></li>
        </ul>
      </div>
    </div>
  </div>
</div>
{/if}

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
      & p,
      ul {
        margin-top: 4rem;
      }

      & ul {
        list-style: none;
      }

      & li {
        border-bottom: 1px solid white;
        width: 45%;
      }

      & li a {
        text-decoration: none;
        color: #fff;
      }

      & a:hover {
        text-decoration: solid;
        color: #06b4e0;
        text-decoration: underline;
      }
    }

    & .age {
      width: 20vw;
    }
  }

  @media (max-width: 1051px) {
      
      .card {
        display: flex;
        flex-direction: column;
      }

      .personal_info {
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        width: 100%;
      }
    }


    @media (max-width: 515px) { 
      .about_me {
        display: flex;
        flex-direction: column;
        width: fit-content;
      }

      .story {
        width: 100%;
        margin-top: 1rem;
      }

      h3, p {
        width: 200px;
      }
    }
</style>
