<script>
  // components
  import NavBar from "../components/layouts/navigation/navbar.svelte";
  import InitalPage from "../components/pages/InitalPage.svelte";
  import WelcomePage from "../components/pages/WelcomePage.svelte";

  //--- about slides
  import AVerseByVerse from "../components/pages/A_VerseByVerse.svelte";
  import BVerseByVerse from "../components/pages/B_VerseByVerse.svelte";
  import CVerseByVerse from "../components/pages/C_VerseByVerse.svelte";
  import DVerseByVerse from "../components/pages/D_VerseByVerse.svelte";
  import EVerseByVerse from "../components/pages/E_VerseByVerse.svelte";
  import FVerseByVerse from "../components/pages/F_VerseByVerse.svelte";
  import GVerseByVerse from "../components/pages/G_VerseByVerse.svelte";

  // states
  let currentPage = 2;
  let currentIconOffset = 0;
  let iconSrc = "assets/images/icons/chat_bubbles.png";

  //   setTimeout(() => {
  //     currentPage = 1;
  //   }, 10000);

  let canRenderNext = true;

  const renderNext = (e) => {
    if (canRenderNext) {
      currentPage = e.detail.view;
      currentIconOffset = e.detail.iconOffset;
      iconSrc = e.detail.iconSrc;

      canRenderNext = false;
      setTimeout(() => {
        canRenderNext = true;
      }, 1500);
    }
  };
</script>

<div>
  {#if currentPage >= 2}<NavBar {iconSrc} leftPx={currentIconOffset} />{/if}
  {#if currentPage === 20}<InitalPage />{/if}
  {#if currentPage === 1}<WelcomePage on:renderNext={renderNext} />{/if}
  {#if currentPage === 2}<AVerseByVerse on:renderNext={renderNext} />{/if}
  {#if currentPage === 3}<BVerseByVerse on:renderNext={renderNext} />{/if}
  {#if currentPage === 4}<CVerseByVerse on:renderNext={renderNext} />{/if}
  {#if currentPage === 5}<DVerseByVerse on:renderNext={renderNext} />{/if}
  {#if currentPage === 6}<EVerseByVerse on:renderNext={renderNext} />{/if}
  {#if currentPage === 7}<FVerseByVerse on:renderNext={renderNext} />{/if}
  {#if currentPage === 8}<GVerseByVerse on:renderNext={renderNext} />{/if}
</div>
