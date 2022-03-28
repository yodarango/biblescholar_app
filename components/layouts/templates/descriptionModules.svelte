<script>
  // comps
  import StandardButton from "../../triggers/buttons/standardButton.svelte";

  // props
  export let title = "";
  export let description = "";
  export let imgSource = "";
</script>

<div class="description-module-wrapper  std-flex-column std-flex-nowrap">
  <div class="title-wrapper"><h1 class="big-title">{title}</h1></div>
  <article class="description-wrapper"><p>{description}</p></article>
  <StandardButton
    text="Next"
    withIcon={true}
    icon="assets/images/icons/arrow.png"
  />
  <div class="image-wrapper">
    <img draggable="false" src={imgSource} alt="mobile comments diagram" />
  </div>
</div>

<style>
  .description-module-wrapper {
    width: 100%;
    height: calc(80% - 15rem);
    margin: 15rem auto 0;
    align-items: flex-end;
    justify-content: flex-start;
  }

  .title-wrapper {
    position: relative;
    max-width: 70rem;
    width: 100%;
    margin: var(--medium-spacing) 0 var(--large-spacing);
    z-index: 2;
  }
  .title-wrapper h1 {
    text-shadow: 2rem 2rem 0.5rem var(--shadow-color);
  }
  .title-wrapper h1,
  .description-wrapper p {
    text-align: right;
    text-shadow: 1rem 1rem 0.2rem var(--shadow-color);
  }

  .description-wrapper {
    max-width: 80rem;
    width: 100%;
    margin: 0 0 var(--xxlarge-spacing);
    position: relative;
    z-index: 2;
  }

  .image-wrapper {
    position: absolute;
    width: 100%;
    bottom: 0;
    z-index: 1;
  }

  .image-wrapper img {
    width: 100%;
    display: block;
    object-fit: contain;
    object-position: center;
  }
</style>
