<script>
  // core
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  // components
  import DescriptionModules from "../layouts/templates/descriptionModules.svelte";

  // props
  const title = "Find 100's Of Locations";
  const description = `Search hundreds of locations by state, city, or zip. You can find helpful information as times of service, driving directions, website, and more `;
  const imgSource = "assets/images/bkgs/churches_big.png";
  const phoneUp = "assets/images/screens/phone_up_6.png";
  const phoneDown = "assets/images/screens/phone_down_6.png";

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
          view: 8,
          iconOffset: 75,
          iconSrc: "assets/images/icons/last_24.png",
        });
      } else {
        dispatch("renderNext", {
          view: 6,
          iconOffset: 50,
          iconSrc: "assets/images/icons/media_content.png",
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
      ? `transform: translate(-5rem, 0rem)`
      : ""}
  />
</div>

<style>
</style>
