<script>
  // components
  import DescriptionModules from "../layouts/templates/descriptionModules.svelte";

  // props
  const title = "Verse By Verse Comments";
  const description = `Born on September 22, 2011, Slavery Footprint is a non-profit organization that works to ens mission of freeing the modern-day slaves.`;
  const imgSource = "assets/images/Africa.png";
</script>

<div class="main-wrapper">
  <DescriptionModules {title} {description} {imgSource} />
</div>

<style>
  .main-wrapper {
    height: 100%;
  }
</style>
