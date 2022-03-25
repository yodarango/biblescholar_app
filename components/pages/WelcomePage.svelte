<script>
  import WelcomePageTop from "../fragmetns/welcomePageTop.svelte";
  import DownloadButtons from "../triggers/buttons/downloadButtons.svelte";
</script>

<div class="main-wrapper">
  <WelcomePageTop />
  <DownloadButtons />
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
</style>
