<script>
  // core
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  // three.js
  // import {
  //   Scene,
  //   PerspectiveCamera,
  //   WebGLRenderer,
  //   HemisphereLight,
  //   AmbientLight,
  //   PointLight,
  //   BoxGeometry,
  //   MeshStandardMaterial,
  //   Mesh,
  //   Color,
  // } from "three";
  // import { GLTFLoader } from "../../helpers/GLTFLoader";

  // components
  import DescriptionModules from "../layouts/templates/descriptionModules.svelte";

  // props
  const title = "Verse By Verse Comments";
  const description = `Born on September 22, 2011, Slavery Footprint is a non-profit organization that works to ens mission of freeing the modern-day slaves.`;
  const imgSource = "assets/images/bkgs/chat_bubbles_big.png";

  // make sure that the user has scrolled the wheel at least three times
  let scrollCount = 0;
  const checkScrollingDistance = (e) => {
    console.log(e);
    console.log(navigator.userAgent);
    scrollCount += 1;
    if (scrollCount >= 2) {
      if (e.deltaY > 0) {
        dispatch("renderNext", {
          view: 3,
          iconOffset: 12.5,
          iconSrc: "assets/images/icons/bulb.png",
        });
      } else {
        dispatch("renderNext", {
          view: 1,
          iconOffset: 0,
          iconSrc: "assets/images/icons/chat_bubbles.png",
        });
      }
      scrollCount = 0;
    }
  };

  //------------------------------------ 3D Model Rendering -----------------------------
</script>

<div class="main-wrapper" on:wheel|nonpassive={checkScrollingDistance}>
  <DescriptionModules {title} {description} {imgSource} />
</div>

<style>
  .main-wrapper {
    height: 100%;
  }
</style>
