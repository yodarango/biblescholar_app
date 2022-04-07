<script>
  let renderCourtain = true;
  setTimeout(() => {
    renderCourtain = false;
  }, 800);
</script>

{#if renderCourtain}
  <div class="courtain">
    <span class="one" />
    <span class="two" />
    <span class="three" />
    <span class="four" />
    <span class="five" />
    <span class="six" />
    <span class="seven" />
    <span class="eight" />
    <span class="nine" />
    <span class="ten" />
  </div>
{/if}

<style>
  :root {
    --animation-speed: 500ms;
  }
  .courtain {
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    position: fixed;
    z-index: 4;
  }

  .courtain span {
    display: block;
    height: 10.2vh;
    width: 110vw;
    border-radius: 10vh;
    position: absolute;
    background: linear-gradient(90deg, var(--graient-one), var(--gradient-two));
  }

  .one {
    top: 0;
    left: -111vw;
    animation: CurtainIntroLeft var(--animation-speed) linear;
  }
  .two {
    top: 10vh;
    right: -111vw;
    animation: CurtainIntroRight var(--animation-speed) linear;
  }
  .three {
    top: 20vh;
    left: -111vw;
    animation: CurtainIntroLeft var(--animation-speed) linear;
  }

  .four {
    top: 30vh;
    right: -111vw;
    animation: CurtainIntroRight var(--animation-speed) linear;
  }
  .five {
    top: 40vh;
    left: -111vw;
    animation: CurtainIntroLeft var(--animation-speed) linear;
  }
  .six {
    top: 50vh;
    right: -111vw;
    animation: CurtainIntroRight var(--animation-speed) linear;
  }
  .seven {
    top: 60vh;
    left: -111vw;
    animation: CurtainIntroLeft var(--animation-speed) linear;
  }
  .eight {
    top: 70vh;
    right: -111vw;
    animation: CurtainIntroRight var(--animation-speed) linear;
  }

  .nine {
    top: 80vh;
    left: -111vw;
    animation: CurtainIntroLeft var(--animation-speed) linear;
  }
  .ten {
    top: 90vh;
    right: -111vw;
    animation: CurtainIntroRight var(--animation-speed) linear;
  }

  @keyframes CurtainIntroLeft {
    0% {
      left: -5vw;
    }
    50% {
      left: -30vw;
    }
    80% {
      left: -60vw;
    }
    100% {
      left: -111vw;
    }
  }

  @keyframes CurtainIntroRight {
    0% {
      right: -5vw;
    }
    50% {
      right: -30vw;
    }
    80% {
      right: -60vw;
    }
    100% {
      right: -111vw;
    }
  }
</style>
