<script>
  //comps
  import WelcomePageTop from "../fragmetns/welcomePageTop.svelte";
  import DownloadButtons from "../triggers/buttons/downloadButtons.svelte";
  import StandardButton from "../triggers/buttons/standardButton.svelte";
</script>

<div class="main-wrapper">
  <WelcomePageTop />
  <DownloadButtons />
  <div class="button-wrapper std-flex-row">
    <button class="std-button with-icon std-flex-row std-flex-nowrap"
      >Start Tour<span
        style="background-image: url(assets/images/icons/arrow.png);"
      /></button
    >
  </div>
  <img
    draggable="false"
    src="assets/images/Africa.png"
    alt="planet earth"
    class="plannet-earth"
  />
</div>

<style>
  .plannet-earth {
    position: absolute;
    width: 80vw;
    bottom: -10rem;
    left: -30rem;
    object-fit: contain;
    object-position: center;
    transform: rotate(-45deg);
    z-index: 1;
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

  @media (min-width: 750px) {
    .button-wrapper {
      width: 30rem;
      margin: 0 0 0 auto;
    }
    .std-button.with-icon {
      max-height: 4.6rem;
      margin: var(--medium-spacing) auto;
    }

    .std-button.with-icon:hover {
      width: 18rem;
    }
  }

  @media (min-width: 1050px) {
    .button-wrapper {
      margin: 0 var(--xlarge-spacing) var(--large-spacing) auto;
    }
    .std-button.with-icon {
      width: 16rem;
      max-height: 5.2rem;
    }

    .std-button.with-icon:hover {
      width: 19rem;
    }
  }
</style>
