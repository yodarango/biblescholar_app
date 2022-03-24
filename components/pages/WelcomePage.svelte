<script>
  import WelcomePageTop from "../fragmetns/welcomePageTop.svelte";
  import DownloadButtons from "../triggers/buttons/downloadButtons.svelte";
</script>

<div class="main-wrapper">
  <WelcomePageTop />
  <DownloadButtons />
  <img
    src="assets/images/Africa.png"
    alt="planet earth"
    class="plannet-earth"
  />
</div>

<style>
  .plannet-earth {
    position: absolute;
    width: 200%;
    bottom: -20%;
    left: -80%;
    object-fit: contain;
    object-position: center;
    transform: rotate(-45deg);
  }
</style>
