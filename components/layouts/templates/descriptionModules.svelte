<script>
  // components
  import EntryCourtain from "../../fragmetns/entryCourtain.svelte";
  import StandardButton from "../../triggers/buttons/standardButton.svelte";

  // props
  export let title = "";
  export let description = "";
  export let imgSource = "";
  export let additionalStyles = "";

  // -------- check whther the user is in mobile
  const UA = navigator.userAgent;
  const mobile =
    /Mobile|Android|iP(hone|od)|IEMobile|BlackBerry|Kindle|Silk-Accelerated|(hpw|web)OS|Opera M(obi|ini)/.test(
      UA
    );

  console.log("is user on mobile? ", mobile);
</script>

<div class="description-module-wrapper  std-flex-column std-flex-nowrap">
  <EntryCourtain />
  <div class="title-wrapper">
    <h1 class={`${!mobile ? "big-title-gradient" : ""} big-title`}>
      {title}
    </h1>
  </div>
  <article class="description-wrapper"><p>{description}</p></article>
  {#if mobile}
    <StandardButton
      withIcon="true"
      icon={"/assets/images/icons/arrow.png"}
      on:renderNextMobile
      text="Next"
    />
  {/if}
  <div class="image-wrapper">
    <img
      draggable="false"
      src={imgSource}
      alt="mobile comments diagram"
      class="bkg-3d"
      style={`${additionalStyles}`}
    />
  </div>
  <!-- <img
    scr="/assets/images/iphone.png"
    alt="iphone 12"
    class="iphone-display"
  /> -->
  <div class="iphone-display-wrapper">
    <div class="iphone-display up" />
    <div class="iphone-display down" />
  </div>
</div>

<style>
  .description-module-wrapper {
    position: relative;
    width: 100%;
    height: calc(80% - 15rem);
    margin: 8rem auto 0;
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

  @keyframes textEntry {
    0% {
      color: transparent;
      opacity: 0;
      text-shadow: 0rem 0rem 0rem var(--shadow-color),
        0px 0px 40px var(--font-color);
      transform: scale(0.8);
      filter: blur(2rem);
    }
    100% {
      color: var(--font-color);
      opacity: 1;
      text-shadow: 2rem 2rem 0.5rem var(--shadow-color),
        0px 0px 0.5px var(--font-color);
      transform: scale(1);
      filter: blur(0);
    }
  }
  .title-wrapper h1,
  .description-wrapper p {
    text-align: right;
    text-shadow: 1rem 1rem 0.2rem var(--shadow-color);
    animation: textEntry 1000ms ease-in;
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
    margin: auto;
    z-index: -1;
    top: 10rem;
    opacity: 0.3;
  }

  .image-wrapper img {
    width: 100%;
    display: block;
    object-fit: contain;
    object-position: center;
    max-width: 70rem;
  }

  .bkg-3d {
    animation: imageIntro 1000ms ease;
  }

  @keyframes imageIntro {
    0% {
      filter: blur(10rem);
      opacity: 0;
    }
    100% {
      filter: blur(0);
      opacity: 1;
    }
  }

  @keyframes imageIntroDesktop {
    0% {
      filter: blur(10rem);
      opacity: 0;
    }
    100% {
      filter: blur(0);
      opacity: 0.5;
    }
  }

  /* ------------------- ipphone model ------------------------- */
  .iphone-display-wrapper {
    width: 100%;
    margin: 0;
    position: relative;
    transform: translateY(-8rem);
  }

  .iphone-display {
    background-image: url("/assets/images/iphone_standing.png");
    background-position: center;
    background-repeat: no-repeat;
    background-size: contain;
    height: 33rem;
    width: 100%;
    margin: 0;
    position: absolute;
  }

  .iphone-display.up {
    background-position: -8rem center;
    z-index: 0;
  }

  .iphone-display.down {
    z-index: 1;
    height: 35rem;
    background-size: 77%;
    background-position: 2rem 10rem;
    background-image: url("/assets/images/iphone_laying.png");
  }

  @media (min-width: 750px) {
    .image-wrapper {
      width: 80%;
      /* transform: translateY(-20rem); */
    }

    .image-wrapper img {
      opacity: 0.5;
    }

    .bkg-3d {
      animation: imageIntroDesktop 1000ms ease;
    }
  }

  @media (min-width: 1050px) {
    .image-wrapper {
      width: 80%;
      margin: auto auto auto 0;
      /* transform: translate(-4rem, -30rem); */
    }
  }

  @media (min-width: 1200px) {
    .description-module-wrapper {
      width: 100%;
      height: calc(80% - 15rem);
      margin: 15rem auto 0;
      align-items: flex-end;
      justify-content: flex-start;
    }
  }
</style>
