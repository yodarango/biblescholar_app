<script>
  // core
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  // components
  import DescriptionModules from "../layouts/templates/descriptionModules.svelte";

  // props
  const title = "Create Quotes";
  const description = `Born on September 22, 2011, Slavery Footprint is a non-profit organization that works to ens mission of freeing the modern-day slaves.`;
  const imgSource = "assets/images/bkgs/quotes.png";

  //----------------- make sure that the user has scrolled the wheel at least three times
  let scrollCount = 0;
  const checkScrollingDistance = (e) => {
    scrollCount += 1;
    if (scrollCount >= 2) {
      if (e.deltaY > 0) {
        dispatch("renderNext", {
          view: 5,
          iconOffset: 37.5,
          iconSrc: "assets/images/icons/sermons.png",
        });
      } else {
        dispatch("renderNext", {
          view: 3,
          iconOffset: 12.5,
          iconSrc: "assets/images/icons/bulb.png",
        });
      }
      scrollCount = 0;
    }
  };

  // --------------- masure media query
  let mediaWidth = window.innerWidth;
  window.addEventListener("resize", () => (mediaWidth = window.innerWidth));
  console.log(mediaWidth);
</script>

<div class="main-wrapper" on:wheel|nonpassive={checkScrollingDistance}>
  <DescriptionModules
    {title}
    {description}
    {imgSource}
    additionalStyles={mediaWidth >= 750 ? `width: 80%;` : `width: 80%;`}
  />
</div>

<style>
  .main-wrapper {
    height: 100%;
  }
</style>
