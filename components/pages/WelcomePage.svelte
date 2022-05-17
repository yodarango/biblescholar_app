<script>
  // core
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  //comps
  import WelcomePageTop from "../fragmetns/welcomePageTop.svelte";
  import DownloadButtons from "../triggers/buttons/downloadButtons.svelte";
</script>

<div class="main-wrapper">
  <WelcomePageTop />
  <DownloadButtons />
  <div class="button-wrapper std-flex-row">
    <button
      class="std-button with-icon std-flex-row std-flex-nowrap"
      on:click={() =>
        dispatch("renderNext", {
          view: 2,
          iconOffset: 0,
          iconSrc: "assets/images/icons/chat_bubbles.png",
        })}
      >Start Tour<span
        style="background-image: url(assets/images/icons/arrow.png);"
      /></button
    >
  </div>
  <video
    class="bkg-video"
    src="assets/Scholarapp_bkg.mov"
    autoplay
    muted
    loop
    playsinline
  >
    <track kind="captions" />
  </video>
</div>

<style>
  .bkg-video {
    position: fixed;
    top: 50%;
    left: 0;
    min-width: 100%;
    min-height: 100%;
    width: auto;
    height: auto;
    z-index: -100;
    transform: translateX(-50%) translateY(-50%);
    background-size: cover;
    animation: videoIntro 3000ms linear;
  }

  /* --------- button --------- */
  .std-button.with-icon {
    width: 13rem;
    overflow: hidden;
    max-height: 4.1rem;
    margin: var(--medium-spacing) var(--xlarge-spacing) var(--medium-spacing)
      auto;
  }

  .std-button.with-icon:hover {
    width: 16rem;
  }

  .std-button.with-icon:active span {
    background-position: 1rem center;
  }

  @keyframes videoIntro {
    0% {
      opacity: 0;
    }
    100% {
      opacity: 1;
    }
  }

  @media (min-width: 750px) {
    .bkg-video {
      top: 50%;
      left: 30%;
    }
    .button-wrapper {
      width: 30rem;
      margin: 0 0 0 auto;
      position: fixed;
      bottom: 5rem;
      right: 8rem;
    }
    .button-wrapper .std-button.with-icon {
      margin: var(--medium-spacing) 0 var(--medium-spacing) auto;
      width: 18rem;
    }

    .std-button.with-icon {
      max-height: 4.6rem;
      margin: var(--medium-spacing) auto;
    }

    .std-button.with-icon:hover {
      width: 19rem;
    }
  }

  @media (min-width: 1050px) {
    .bkg-video {
      top: 50%;
      left: 50%;
    }
    .button-wrapper {
      bottom: 5rem;
      right: 15rem;
    }

    .std-button.with-icon {
      max-height: 5.2rem;
    }
  }

  @media (min-width: 1400px) {
    .button-wrapper {
      bottom: 10rem;
      right: 20rem;
    }
  }
</style>
