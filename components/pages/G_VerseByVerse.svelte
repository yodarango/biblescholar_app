<script>
  // core
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  // components
  import DescriptionModules from "../layouts/templates/descriptionModules.svelte";

  // props
  const title = "See Content By Others on 24 Hour Basis";
  const description = `Born on September 22, 2011, Slavery Footprint is a non-profit organization that works to ens mission of freeing the modern-day slaves.`;
  const imgSource = "assets/images/bkgs/last_24_big.png";

  // make sure that the user has scrolled the wheel at least three times
  let scrollCount = 0;
  const checkScrollingDistance = (e) => {
    scrollCount += 1;
    if (scrollCount >= 2) {
      if (e.deltaY > 0) {
        dispatch("renderNext", {
          view: 1,
          iconOffset: 0,
          iconSrc: "assets/images/icons/chat_bubbles.png",
        });
      } else {
        dispatch("renderNext", {
          view: 7,
          iconOffset: 62.5,
          iconSrc: "assets/images/icons/churches.png",
        });
      }
      scrollCount = 0;
    }
  };
</script>

<div class="main-wrapper" on:wheel|nonpassive={checkScrollingDistance}>
  <DescriptionModules {title} {description} {imgSource} />
</div>

<style>
  .main-wrapper {
    height: 100%;
  }
</style>
