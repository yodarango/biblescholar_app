<script>
  let currInterval = 0;

  const introAnimation = setInterval(() => {
    currInterval = currInterval < 3 ? currInterval + 1 : 0;

    console.log(currInterval);
    cleanupInterval();
  }, 3000);

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
    <img src={"assets/images/logo.png"} alt="ah1h1 logo" class="logo" />
  {/if}
</div>

<style>
  .animation-wrapper {
    width: 100%;
  }

  .intro-text {
    width: 100%;
    text-align: center;
    font-size: 5rem;
    opacity: 0;
    animation: IntroText 3s ease-in-out;
  }

  .logo {
    width: 100%;
    object-fit: center;
    object-position: center;
    animation: IntroLogo 3s ease-in-out;
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
</style>
