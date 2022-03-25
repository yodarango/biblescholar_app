<script>
  // props
  export let iconSrc;
</script>

<div class="navbar-link-wrapper">
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
    position: relative;
    width: 6rem;
    height: 6rem;
  }
  .circle {
    position: absolute;
    width: 6em;
    height: 6em;
    border-radius: 50%;
    border: 0.5rem solid var(--secondary-color);
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
    width: 1.5em;
    height: 1.5em;
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
    width: 6em;
    height: 6em;
    transform: translate(-0.5em, -1em);
    object-fit: contain;
    object-position: center;
  }
</style>
