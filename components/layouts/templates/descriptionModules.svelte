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
      addStyles={"position: relative; z-index: 2;"}
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
  <div class={`${mobile ? "mobile" : ""} iphone-display-wrapper`}>
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
    max-width: 80rem;
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

  /* ------------------- iphone model ------------------------- */
  .iphone-display-wrapper.mobile,
  .iphone-display-wrapper {
    width: 100%;
    margin: 0;
    position: relative;
    transform: translateY(-8rem);
  }

  .iphone-display-wrapper {
    transform: none;
  }

  .iphone-display {
    background-image: url("/assets/images/iphone_standing.png");
    background-position: center;
    background-repeat: no-repeat;
    background-size: contain;
    height: 33rem;
    width: 100%;
    margin: 0;
    left: 0;
    top: 0;
    position: absolute;
  }

  .iphone-display.up {
    background-position: -8rem center;
    z-index: 0;
    animation: iPhoneModelEntryUp 2500ms cubic-bezier(0.075, 0.82, 0.165, 1);
  }

  .iphone-display.down {
    z-index: 1;
    height: 35rem;
    max-width: 35rem;
    background-size: 77%;
    background-position: 2rem 10rem;
    background-image: url("/assets/images/iphone_laying.png");
    animation: iPhoneModelEntryDown 2500ms cubic-bezier(0.075, 0.82, 0.165, 1);
  }

  @keyframes iPhoneModelEntryUp {
    0% {
      opacity: 0.3;
      left: -20rem;
    }
    100% {
      opacity: 1;
      left: 0rem;
    }
  }

  @keyframes iPhoneModelEntryDown {
    0% {
      opacity: 0.3;
      top: 25rem;
    }
    100% {
      opacity: 1;
      top: 0rem;
    }
  }

  @media (min-width: 500px) {
    .iphone-display-wrapper {
      transform: none;
    }
    .iphone-display.down {
      top: 55rem;
      bottom: 0;
      left: 0;
      right: 0;
      max-width: 55rem;
      margin: auto;
      background-position: center;
    }

    .iphone-display.up {
      background-position: -8rem center;
      z-index: 0;
      height: 45rem;
    }

    @keyframes iPhoneModelEntryDown {
      0% {
        opacity: 0.3;
        top: 85rem;
      }
      100% {
        opacity: 1;
        top: 55rem;
      }
    }
  }

  @media (min-width: 750px) {
    .image-wrapper {
      width: 80%;
      transform: translate(15rem, 15rem);
    }

    .image-wrapper img {
      opacity: 0.5;
    }

    .bkg-3d {
      animation: imageIntroDesktop 1000ms ease;
    }

    /* ------------- iphone model rendering -------------- */
    .iphone-display-wrapper {
      max-width: 75rem;
      transform: translateY(-3rem);
      margin: auto;
    }

    .iphone-display.down {
      top: 60rem;
      bottom: 0;
      left: 0;
      right: 0;
      max-width: 65rem;
      height: 45rem;
      margin: auto;
      background-position: 15rem center;
    }

    .iphone-display.up {
      background-position: -2rem center;
      z-index: 0;
      height: 50rem;
    }

    @keyframes iPhoneModelEntryDown {
      0% {
        opacity: 0.3;
        top: 85rem;
      }
      100% {
        opacity: 1;
        top: 60rem;
      }
    }
  }

  @media (min-width: 1050px) {
    .image-wrapper {
      width: 80%;
      margin: 0;
      left: 50%;
      transform: none;
      margin: 0;
    }
  }

  @media (min-width: 1200px) {
    .description-module-wrapper {
      width: 100%;
      height: calc(80% - 15rem);
      margin: 15rem auto 0;
      align-items: flex-end;
      justify-content: flex-start;
      flex-wrap: wrap;
    }

    .title-wrapper,
    .description-wrapper {
      width: 45%;
    }

    /* -------- iphone model -------- */
    .iphone-display-wrapper {
      width: 50%;
      transform: translate(-30rem, -30rem);
    }
  }
</style>
