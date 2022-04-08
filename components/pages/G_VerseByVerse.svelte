<script>
  // core
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  // components
  import DescriptionModules from "../layouts/templates/descriptionModules.svelte";

  // props
  const title = "What's Going on";
  const description = `See what everyone has shared in the last 24 hours as well as exclusive daily content by differnet collaborators`;
  const imgSource = "assets/images/bkgs/last_24_big.png";

  // render next component on mobile
  const renderNextMobile = () => {
    scrollCount = 3;
    checkScrollingDistance({ deltaY: 1 });
  };

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
  <DescriptionModules
    {title}
    {description}
    {imgSource}
    on:renderNextMobile={renderNextMobile}
  />
</div>

<style>
</style>
