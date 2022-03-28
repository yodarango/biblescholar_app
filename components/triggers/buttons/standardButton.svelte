<script>
  export let text;
  export let withIcon = false;
  export let icon = "";
  export let addStyles;
</script>

<div class="button-wrapper">
  {#if withIcon === false}<button class="std-button">{text}</button>{:else}
    <button
      class="std-button with-icon std-flex-row std-flex-nowrap"
      style={`${addStyles}`}
      >{text}<span style={`background-image: url(${icon});`} /></button
    >{/if}
</div>
