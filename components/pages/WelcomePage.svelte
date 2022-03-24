<script>
let welcomeTextRaw = 'Knowing the word one verse at a time'
let welcomeText = [...welcomeTextRaw]
let renderText = []
let currentChar = 0

console.log(welcomeText)
setInterval(() => {
    if(currentChar < welcomeText.length){
    renderText = [...renderText, welcomeText[currentChar]]
    currentChar += 1
    }
}, 100);
</script>

<div class="main-wrapper">
  <div class="welcome-wrapper">
      <h1 class="welcome-title"><span class="gradient-text welcome">WELCOME</span></h1>
      <h1 class="welcome-sub-title"><span class="gradient-text to-scholar">TO SCHOLAR</span></h1>
      <p class="welcome-text">{#each welcomeTextRaw as char}
      <span class="">{char ==  " " ? - : char}</span>
      {/each}</p>
  </div>
</div>

<style>
    .welcome-wrapper{
        margin-top: 10rem;
    }
    .welcome-title, .welcome-sub-title{ 
        font-size: 5rem;
        width: 100%;
        line-height: 1em;
        margin: var(--xsmall-spacing) 0;
        position: relative;
        left: 0;
        animation: TextSlideLeft 2000ms ease;
    }

    .welcome-sub-title{
        animation: TextSlideRight 2000ms ease;
    }

    .gradient-text{
        text-align: left;
    }

    .welcome-sub-title{
        text-align: right;
    }
    .welcome-text{
        width: 100%;
        margin: var(--medium-spacing) auto;
        font-size: var(--sub-title-font);
        line-height: 1em;
        text-align: center;
    }

    @keyframes TextSlideLeft {
        0%{
            left: -100%;
            opacity: 0;
        }
        100%{
            left: 0%;
            opacity: 1;
        }
    }
    @keyframes TextSlideRight {
        0%{
            left: 100%;
            opacity: 0;
        }
        100%{
            left: 0%;
            opacity: 1;
        }
    }

</style>