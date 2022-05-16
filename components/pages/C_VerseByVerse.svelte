<script>
  // core
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  // components
  import DescriptionModules from "../layouts/templates/descriptionModules.svelte";

  // props
  const title = "Quotes Are Awesome";
  const description = `Everyone loves a good quote. They are inspirational, easy to remember, and concise enough to get a point across in just a few words. Let the community see yours`;
  const imgSource = "assets/images/bkgs/quotes.png";
  const phoneUp = "assets/images/screens/phone_up_3.png";
  const phoneDown = "assets/images/screens/phone_down_3.png";

  // render next component on mobile
  const renderNextMobile = () => {
    scrollCount = 3;
    checkScrollingDistance({ deltaY: 1 });
  };

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
</script>

<div class="main-wrapper" on:wheel|nonpassive={checkScrollingDistance}>
  <DescriptionModules
    {title}
    {description}
    {imgSource}
    {phoneDown}
    {phoneUp}
    on:renderNextMobile={renderNextMobile}
    additionalStyles={mediaWidth >= 750
      ? `transform: translate(5rem, -5rem); width: 80%;`
      : ""}
  />
</div>

<style>
</style>
