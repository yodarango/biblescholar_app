<script>
  // props
  export let iconSrc;
  export let leftPx;

  let windowWidth = window.innerWidth;

  window.addEventListener("resize", () => {
    windowWidth = window.innerWidth;
  });
</script>

<div
  class="navbar-link-wrapper"
  style={windowWidth <= 950 ? `left: ${leftPx}%` : `top: ${leftPx}vh`}
>
  <div class="circle">
    <img
      draggable="false"
      src={iconSrc}
      alt="navigation item"
      class="nav-link-icon"
    />
  </div>
  <div class="tip" />
</div>

<style>
  .navbar-link-wrapper {
    position: absolute;
    width: 4rem;
    height: 4rem;
    left: 0;
    top: 0;
    transition: 300ms ease;
    z-index: 5;
  }
  .circle {
    position: absolute;
    width: 100%;
    height: 100%;
    border-radius: 50%;
    border: 0.3rem solid var(--secondary-color);
    background-color: #94939d;
    z-index: 2;
  }
  /* --------- triangle                                            */
  .tip {
    position: absolute;
    top: -0.7rem;
    bottom: 0;
    left: 0;
    right: 0;
    margin: 0 auto;
    background-color: var(--secondary-color);
  }
  .tip:before,
  .tip:after {
    content: "";
    position: absolute;
    background-color: inherit;
  }
  .tip,
  .tip:before,
  .tip:after {
    width: 0.8em;
    height: 0.8em;
    border-top-right-radius: 30%;
  }
  .tip {
    transform: rotate(-60deg) skewX(-30deg) scale(1, 0.866);
  }
  .tip:before {
    transform: rotate(-135deg) skewX(-45deg) scale(1.414, 0.707)
      translate(0, -50%);
  }
  .tip:after {
    transform: rotate(135deg) skewY(-45deg) scale(0.707, 1.414) translate(50%);
  }

  .nav-link-icon {
    width: 4.5rem;
    height: 4.5rem;
    transform: translate(-0.5em, -0.5em);
    object-fit: contain;
    object-position: center;
    animation: iconEntry 500ms ease;
  }

  @keyframes iconEntry {
    0% {
      width: 2rem;
      height: 2rem;
      transform: translate(-1em, -1em);
      opacity: 0;
    }
    100% {
      width: 4.5rem;
      height: 4.5rem;
      transform: translate(-0.5em, -0.5em);
      opacity: 1;
    }
  }

  @media (min-width: 950px) {
    .navbar-link-wrapper {
      position: absolute;
      width: 6rem;
      height: 6rem;
      left: 2rem;
    }
    .nav-link-icon {
      width: 6.5rem;
      height: 6.5rem;
      transform: translate(0.3rem, 0.3rem);
    }
    .tip {
      top: 1.5rem;
      left: -4rem;
      transform: rotate(-30deg) skewX(-30deg) scale(1, 0.866);
    }
  }

  /* @media (min-width: 1300px) {
    .navbar-link-wrapper {
      left: -1vw;
    }
  } */
</style>
