<script>
  // components
  import NavbarLink from "../../triggers/buttons/navbar_link.svelte";

  // props
  export let iconSrc;
  export let leftPx;
</script>

<div class="global-navigation--gradient" />
<nav class="global-navigation--links-wrapper">
  <NavbarLink {iconSrc} {leftPx} />
</nav>

<style>
  .global-navigation--gradient {
    width: 100vw;
    height: 1rem;
    position: fixed;
    top: 0;
    left: 0;
    background-image: linear-gradient(
      45deg,
      var(--graient-one),
      var(--gradient-two),
      var(--graient-one),
      var(--gradient-two)
    );
    background-size: 400% 100%;
    animation: NavbarGradient 2000ms ease infinite;
    animation-direction: alternate;
    z-index: 5;
  }

  @keyframes NavbarGradient {
    0% {
      background-position: 0%;
    }
    100% {
      background-position: 100%;
    }
  }
  .global-navigation--links-wrapper {
    width: 100vw;
    height: 5rem;
    display: block;
    position: fixed;
    top: 3rem;
    left: 4%;
  }

  @media (min-width: 1050px) {
    .global-navigation--gradient {
      width: 2rem;
      height: 100vh;
      background-size: 100% 400%;
    }
    @keyframes NavbarGradient {
      0% {
        background-position: 100% 0%;
      }
      100% {
        background-position: 100% 100%;
      }
    }
  }
</style>
