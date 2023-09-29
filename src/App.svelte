<script lang="ts">
  import Plumbing from "./tutorials/Plumbing.svelte";
  import Auto from "./tutorials/Auto.svelte";
  import Emilio from "./tutorials/Emilio.svelte";
  import Cab from "./tutorials/Cab.svelte";
  import Surveyor from "./tutorials/Surveyor.svelte";
  import autoImg from "./assets/Auto.png";
  import surveyImg from "./assets/Surveyor.png";
  import cabImg from "./assets/CabService.png";
  import emilioImg from "./assets/Emilio.png";
  import plumbingImg from "./assets/Plumbing.png";

  let tutorials = [
    {
      img: plumbingImg,
      component: Plumbing,
      desc: "Bottom-Left",
    },
    {
      img: autoImg,
      component: Auto,
      desc: "Centered w/ Bottom Bar",
    },
    {
      img: emilioImg,
      component: Emilio,
      desc: "Side-by-Side",
    },
    {
      img: cabImg,
      component: Cab,
      desc: "Centered",
    },
    {
      img: surveyImg,
      component: Surveyor,
      desc: "Corners",
    },
  ];

  let activeTutorial;
</script>

{#if !activeTutorial}
  <h1>Layout with Flexbox</h1>
  <h3>A series of step-by-step examples</h3>
  <div class="menu">
    {#each tutorials as tutorial}
      <button on:click={() => (activeTutorial = tutorial)}>
        <img src={tutorial.img} style="width:3in" />
        <div>{tutorial.desc}</div>
      </button>
    {/each}
  </div>
{:else}
  <button on:click={() => (activeTutorial = null)}>See other tutorials</button>
  <svelte:component this={activeTutorial.component} />
{/if}

<style>
  .menu {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    justify-content: center;
    align-items: center;
  }
  h1,
  h3 {
    margin: 0;
    text-align: center;
  }
</style>
