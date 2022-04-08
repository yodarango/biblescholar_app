<script>
  // core
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  // components
  import DescriptionModules from "../layouts/templates/descriptionModules.svelte";

  // props
  const title = "Share Your Thoughts";
  const description = `Engage with the community by sharing your thoughts about particular biblical topics that are of interest to you`;
  const imgSource = "assets/images/bkgs/bulb_big.png";

  // render next component on mobile
  const renderNextMobile = () => {
    scrollCount = 3;
    checkScrollingDistance({ deltaY: 1 });
  };

  // ------------------ make sure that the user has scrolled the wheel at least three times
  let scrollCount = 0;
  const checkScrollingDistance = (e) => {
    scrollCount += 1;
    if (scrollCount >= 2) {
      if (e.deltaY > 0) {
        dispatch("renderNext", {
          view: 4,
          iconOffset: 25,
          iconSrc: "assets/images/icons/quote.png",
        });
      } else {
        dispatch("renderNext", {
          view: 2,
          iconOffset: 0,
          iconSrc: "assets/images/icons/chat_bubbles.png",
        });
      }
      scrollCount = 0;
    }
  };

  // --------------- masure media query
  let mediaWidth = window.innerWidth;
  window.addEventListener("resize", () => (mediaWidth = window.innerWidth));
</script>

<div class="main-wrapper" on:wheel|nonpassive={checkScrollingDistance}>
  <DescriptionModules
    {title}
    {description}
    {imgSource}
    on:renderNextMobile={renderNextMobile}
    additionalStyles={mediaWidth >= 750
      ? `transform: translateY(-5rem); width: 80%;`
      : ""}
  />
</div>

<style>
</style>
