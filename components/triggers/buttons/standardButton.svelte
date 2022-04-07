<script>
  // svelte
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  export let text;
  export let withIcon = false;
  export let icon = "";
  export let addStyles;
</script>

<div class="button-wrapper">
  {#if withIcon === false}<button
      class="std-button"
      on:click={() => dispatch("renderNextMobile")}>{text}</button
    >{:else}
    <button
      class="std-button with-icon std-flex-row std-flex-nowrap"
      style={`${addStyles}`}
      on:click={() => dispatch("renderNextMobile")}
      >{text}<span style={`background-image: url(${icon});`} /></button
    >{/if}
</div>
