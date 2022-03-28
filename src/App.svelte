<script>
  // components
  import InitalPage from "../components/pages/InitalPage.svelte";
  import WelcomePage from "../components/pages/WelcomePage.svelte";

  //--- about slides
  import AVerseByVerse from "../components/pages/A_VerseByVerse.svelte";

  // states
  let currentPage = 1;

  // setTimeout(() => {
  //   currentPage = 2;
  // }, 13000);
</script>

<main class="global-wrapper">
  {#if currentPage === 100}<InitalPage />{/if}
  {#if currentPage === 1}<WelcomePage />{/if}
  {#if currentPage === 3}<AVerseByVerse />{/if}
</main>
