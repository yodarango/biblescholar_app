<script>
  let currInterval = 0;

  const introAnimation = setInterval(() => {
    currInterval = currInterval < 3 ? currInterval + 1 : 0;

    console.log(currInterval);
    cleanupInterval();
  }, 2000);

  const cleanupInterval = () => {
    currInterval == 3 ? clearInterval(introAnimation) : null;
  };
</script>

<div class="animation-wrapper">
  {#if currInterval === 0}
    <h1 class="intro-text"><span class="gradient-text">SHOW</span></h1>
  {:else if currInterval === 1}
    <h1 class="intro-text"><span class="gradient-text">THYSELF</span></h1>
  {:else if currInterval === 2}
    <h1 class="intro-text"><span class="gradient-text">APPROVED</span></h1>
  {:else if currInterval === 3}
    <img
      draggable="false"
      src={"assets/images/logo.png"}
      alt="ah1h1 logo"
      class="logo"
    />
  {/if}
</div>

<style>
  .animation-wrapper {
    width: 100%;
    position: fixed;
    top: calc(50vh - 2rem);
    left: 0;
    bottom: 0;
    right: 0;
    margin: auto;
  }

  .intro-text {
    width: 100%;
    text-align: center;
    font: var(--title-font);
    opacity: 0;
    animation: IntroText 2000ms ease-in-out;
  }

  .logo {
    width: 10rem;
    margin: auto;
    display: block;
    object-fit: center;
    object-position: center;
    animation: IntroLogo 3s ease-in-out;
    max-width: 50rem;
    position: absolute;
    top: 0;
    left: 0;
    bottom: calc(50vh + 2rem);
    right: 0;
  }

  @keyframes IntroText {
    0% {
      opacity: 0;
    }
    50% {
      opacity: 1;
    }
    100% {
      opacity: 0;
    }
  }

  @keyframes IntroLogo {
    0% {
      opacity: 0;
    }
    100% {
      opacity: 1;
    }
  }

  @media (min-width: 750px) {
    .logo {
      width: 15rem;
    }
  }
</style>
