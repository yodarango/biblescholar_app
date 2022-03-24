<script>
  let welcomeTextRaw = "Knowing the word one verse at a time";
  let welcomeText = [...welcomeTextRaw];
  let renderText = [];
  let currentChar = 0;

  // animation for the tiel
  const introTitleFunc = () => {
    const timer = setInterval(() => {
      if (currentChar < welcomeText.length) {
        renderText = [...renderText, welcomeText[currentChar]];
        currentChar += 1;
      } else {
        clearInterval(timer);
      }
    }, 80);
  };

  setTimeout(() => {
    introTitleFunc();
  }, 2000);
</script>

<div class="main-wrapper">
  <div class="welcome-wrapper">
    <h1 class="welcome-title">
      <span class="gradient-text welcome">WELCOME</span>
    </h1>
    <h1 class="welcome-sub-title">
      <span class="gradient-text to-scholar">TO SCHOLAR</span>
    </h1>
    <p class="welcome-text">
      {#each renderText as char}
        <span class="intro-text-letter">{char}</span>
      {/each}
    </p>
  </div>
</div>

<style>
  .main-wrapper {
    width: 100%;
  }

  .welcome-wrapper {
    margin-top: 10rem;
  }

  .welcome-title,
  .welcome-sub-title {
    font: var(--title-font);
    width: 100%;
    line-height: 1em;
    margin: var(--xsmall-spacing) 0;
    position: relative;
    left: 0;
    animation: TextSlideLeft 2000ms ease;
  }

  .welcome-sub-title {
    animation: TextSlideRight 2000ms ease;
  }

  .gradient-text {
    text-align: left;
  }

  .welcome-sub-title {
    text-align: right;
  }
  .welcome-text {
    width: 100%;
    margin: var(--medium-spacing) auto;
    line-height: 1.5em;
    text-align: left;
    height: 2rem;
  }

  .intro-text-letter {
    animation: IntroTextLetter 2000ms ease-in;
  }

  @keyframes TextSlideLeft {
    0% {
      left: -100%;
      opacity: 0;
    }
    100% {
      left: 0%;
      opacity: 1;
    }
  }
  @keyframes TextSlideRight {
    0% {
      left: 100%;
      opacity: 0;
    }
    100% {
      left: 0%;
      opacity: 1;
    }
  }

  @keyframes IntroTextLetter {
    0% {
      opacity: 0;
      transform: scale(1.2);
      text-shadow: 1px 1px 2px var(--font-color);
    }
    50% {
      text-shadow: 30px 30px 30px var(--font-color);
    }
    100% {
      opacity: 1;
      transform: none;
      text-shadow: none;
    }
  }
</style>
