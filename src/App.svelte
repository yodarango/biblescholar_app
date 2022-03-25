<script>
  // components
  import InitalPage from "../components/pages/InitalPage.svelte";
  import WelcomePage from "../components/pages/WelcomePage.svelte";

  //--- about slides
  import AVerseByVerse from "../components/pages/A_VerseByVerse.svelte";

  // states
  const initialPoints = [];

  const mainWrapper = document.querySelector(".global-wrapper");

  mainWrapper.addEventListener("wheel", callback, { passive: false });
  const drag = (e) => {
    initialPoints[0] = e.clientX;
    initialPoints[1] = e.clientY;
  };
  const stopDrage = (e) => {
    console.log(initialPoints);
  };
</script>

<main class="global-wrapper" on:mousedown={drag} on:mouseup={stopDrage}>
  <!-- <InitalPage /> -->
  <!-- <WelcomePage /> -->
  <AVerseByVerse />
</main>
