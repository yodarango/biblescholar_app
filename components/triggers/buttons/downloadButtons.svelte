<section class="std-flex-row std-flex--nowrap buttons-wrapper">
  <a
    href="https://apps.apple.com/us/app/girlspring/id1520838902"
    class="small-button download-button apple-btn std-flex-row std-flex--nowrap"
  >
    <div class="apple-logo-btn">
      <span class="right" />
      <span class="bottom" />
      <span class="left" />
    </div>
    <span class="app-store-btn-text">App Store</span>
  </a>
  <a
    href="https://play.google.com/store?utm_source=na_Med&utm_medium=hasem&utm_content=Oct0120&utm_campaign=Evergreen&pcampaignid=MKT-EDR-na-us-1000189-Med-hasem-py-Evergreen-Oct0120-Text_Search_BKWS-id_101419_%7cEXA%7cONSEM_kwid_43700023142506860&gclsrc=ds&gclsrc=ds"
    class="small-button download-button google-play-btn std-flex-row std-flex--nowrap"
  >
    <div class="google-play-logo-btn">
      <span class="blue" />
      <span class="red" />
      <span class="green" />
      <span class="yellow" />
      <span class="google-shadow" />
    </div>
    <span class="google-play-btn-text">Play Store</span>
  </a>
</section>

<style>
  .buttons-wrapper {
    position: relative;
    z-index: 3;
    width: 20rem;
    margin: 10rem 0 var(--large-spacing) auto;
    justify-content: space-around;
    align-items: center;
  }

  .download-button {
    margin: var(--medium-spacing) 0;
    transition: 300ms ease;
  }

  .apple-btn:hover {
    box-shadow: 0.5px 0.5px 30px 0px #7bbfff62,
      -0.5px -0.5px 30px 0px rgba(123, 191, 255, 0.486);
  }

  .app-store-btn-text,
  .google-play-btn-text {
    font: var(--button-font);
    font-size: 1.5rem;
    display: none;
    margin-left: var(--xsmall-spacing);
    animation: ButtonText 300ms ease;
  }

  @keyframes ButtonText {
    0% {
      display: none;
      opacity: 0;
    }
    33% {
      display: inline-flex;
    }
    100% {
      opacity: 1;
    }
  }
  /* ------------------ apple logo button  */
  .apple-logo-btn {
    position: relative;
    width: 4.5rem;
    height: 4.5rem;
  }

  .apple-logo-btn span {
    width: 0.5rem;
    height: 3rem;
    display: block;
    background-color: #42a4ff;
    border-radius: 0.5rem;
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    margin: auto;
  }

  .apple-logo-btn:hover span {
    box-shadow: 1px 1px 5px #67c7ff;
  }

  .apple-logo-btn .right {
    transform: rotate(-32deg);
    right: -0.8rem;
  }

  .apple-logo-btn .left {
    transform: rotate(32deg);
    left: -0.8rem;
  }

  .apple-logo-btn .bottom {
    transform: rotate(90deg);
    top: 1rem;
  }

  /* --------------- Google play button          */
  .google-play-btn:hover {
    box-shadow: 0.5px 0.5px 30px 0px #24ad468a, -0.5px -0.5px 30px 0px #24ad468a;
  }
  .google-play-logo-btn {
    position: relative;
    width: 3rem;
    height: 3rem;
  }
  .google-play-logo-btn span {
    position: absolute;
    display: block;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    margin: auto;
    z-index: 4;
  }

  .google-play-logo-btn:hover {
    filter: drop-shadow(1px 1px 10px #24ad47);
  }

  .google-play-logo-btn .blue {
    clip-path: polygon(55% 50%, 0 0, 0 100%);
    background-color: #42a4ff;
    z-index: 3;
  }
  .google-play-logo-btn .red {
    clip-path: polygon(0% 0%, 0 100%, 75% 65%);
    background-color: #ff4040;
    z-index: 2;
  }
  .google-play-logo-btn .green {
    clip-path: polygon(0% 0%, 0 100%, 75% 35%);
    background-color: #24ad47;
    z-index: 2;
  }
  .google-play-logo-btn .yellow {
    clip-path: polygon(100% 50%, 75% 35%, 20% 50%, 75% 65%);
    background-color: #ffd001;
    z-index: 1;
  }

  @media (min-width: 750px) {
    .buttons-wrapper {
      position: relative;
      z-index: 3;
      width: 30rem;
      margin: 10rem var(--xlarge-spacing) var(--large-spacing) auto;
    }

    .small-button:hover {
      width: 15rem;
    }
    .small-button:hover .google-play-btn-text,
    .small-button:hover .app-store-btn-text {
      animation: ButtonText 500ms ease;
      display: inline-block;
    }

    @keyframes ButtonText {
      0% {
        opacity: 0;
        transform: scale(0);
      }
      80% {
        transform: scale(1);
      }
      100% {
        opacity: 1;
        transform: none;
      }
    }
  }
</style>
