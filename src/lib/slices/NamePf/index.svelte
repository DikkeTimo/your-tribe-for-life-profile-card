<script>
  /** @type {import("@prismicio/client").Content.NamePfSlice} */
  export let slice;
</script>

<section
  data-slice-type={slice.slice_type}
  data-slice-variation={slice.variation}
>
  Placeholder component for {slice.slice_type} (variation: {slice.variation})
  Slices
</section>

<!-- <script>
  /** @type {import("@prismicio/client").Content.NaamSlice} */

  export let slice;
</script>

<section data-slice-type={slice.slice_type} data-slice-variation={slice.variation}>
  {#each slice.primary.name as item}
    <p>{item.text}</p>
  {/each}
</section> -->

<!-- <pre>
	{JSON.stringify(slice, null, 2)}
</pre> -->
