<script>
  // core
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  // components
  import DescriptionModules from "../layouts/templates/descriptionModules.svelte";

  // props
  const title = "Browse Tons Of Content";
  const description = `From preachings, to podcast channels, websites, articles and more; Search the database for any kind of content you desire`;
  const imgSource = "assets/images/bkgs/media_content_big.png";

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
          view: 7,
          iconOffset: 62.5,
          iconSrc: "assets/images/icons/churches.png",
        });
      } else {
        dispatch("renderNext", {
          view: 5,
          iconOffset: 37.5,
          iconSrc: "assets/images/icons/sermons.png",
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
