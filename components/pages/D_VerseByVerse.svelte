<script>
  // core
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  // components
  import DescriptionModules from "../layouts/templates/descriptionModules.svelte";

  // props
  const title = "Upload Sermon Notes";
  const description = `We are a body and we all benefit from each other's ministry. Upload your sermon notes to help, encourage and inspire the community`;
  const imgSource = "assets/images/bkgs/sermons_big.png";
  const phoneUp = "assets/images/screens/phone_up_4.png";
  const phoneDown = "assets/images/screens/phone_down_4.png";

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
          view: 6,
          iconOffset: 50,
          iconSrc: "assets/images/icons/media_content.png",
        });
      } else {
        dispatch("renderNext", {
          view: 4,
          iconOffset: 25,
          iconSrc: "assets/images/icons/quote.png",
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
    additionalStyles={mediaWidth >= 750 ? `transform: translateX(-5rem);` : ""}
  />
</div>

<style>
</style>
