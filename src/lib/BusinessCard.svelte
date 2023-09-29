<script lang="ts">
  import { onMount } from "svelte";
  import prettify from "html-prettify";
  import github from "svelte-highlight/styles/github";
  import { html_beautify } from "js-beautify";
  import { HighlightAuto } from "svelte-highlight";
  export let aspect = "L";
  export let style: string = "";
  export let outline = true;
  let mainEl: HTMLDivElement;
  let code: string = "";

  function showCode() {
    code = mainEl.outerHTML;
    code = code.replace(/;\s*/g, ";\n\t");
    code = code.replace('style="', 'style="\n\t');
    code = code.replace(/class="s-\S*\s*/g, 'class="');
    code = code.replace("</main>", "\n</main>");
    code = html_beautify(code);
  }
  onMount(() => showCode());
</script>

<svelte:head>
  {@html github}
</svelte:head>

<div class="two-column">
  <div class="main-container">
    <main
      bind:this={mainEl}
      class:highlight={outline}
      class:landscape={aspect == "L"}
      class:potrait={aspect != "L"}
      {style}
    >
      <slot />
    </main>
    <button on:click={() => (outline = !outline)}>
      {#if !outline}
        Outline divs
      {:else}
        Remove outlines
      {/if}
    </button>
  </div>
  <div>
    {#if !code}<button on:click={showCode}>Show Code</button>{/if}
    <div class="code">
      <HighlightAuto {code} />
    </div>
  </div>
</div>

<style>
  .two-column {
    display: flex;
    justify-content: center;
    gap: 8px;
  }
  .code {
    text-align: left;
  }
  .highlight :global(div) {
    padding: 1px;
    margin: 1px;
  }
  .highlight > :global(div) {
    border: 1px solid red;
  }
  .highlight > :global(div > div) {
    border: 1px solid green;
  }
  .highlight > :global(div > div > div) {
    border: 1px solid pink;
  }

  .highlight > :global(div > div > div div) {
    border: 1ps solid grey;
  }

  .main-container button {
    position: absolute;
    top: 0;
    right: 0;
    font-size: small;
  }
  .main-container {
    position: relative;
  }

  main {
    border: 1px solid black;
    margin: auto;
    margin-top: 42px;
    margin-bottom: 16px;
    background-color: white;
    color: black;
  }
  .landscape {
    width: 3.5in;
    height: 2in;
  }
  .portrait {
    width: 2in;
    height: 3.5in;
  }
</style>
