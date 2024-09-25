<script context="module">
  let count = 0;
</script>
<script lang="ts">
  import { onMount } from "svelte";
  import prettify from "html-prettify";
  import github from "svelte-highlight/styles/github";
  import { html_beautify, css_beautify } from "js-beautify";
  import { HighlightAuto } from "svelte-highlight";
  export let aspect = "L";
  export let css : string = "";
  import { outlineMode } from "../settings";
  let htmlCode: string = "";
  let cssCode : string = "";
  export let style = '';
  let myId : string;
  function showCode() {
    count++;
    myId = 'business-demo-'+count;
    if (style) {
      mainEl.style = style;
    }
    htmlCode = mainEl.outerHTML;
    htmlCode = htmlCode.replace(/;\s*/g, ";\n\t");
    htmlCode = htmlCode.replace('style="', 'style="\n\t');
    htmlCode = htmlCode.replace(/class="s-\S*\s*/g, 'class="');
    htmlCode = htmlCode.replace("</main>", "\n</main>");
    htmlCode = html_beautify(htmlCode);
    // Now handle CSS...
    let styleElement = outerEl.querySelector('style');
    if (!styleElement) {
      styleElement = document.createElement('style');
      outerEl.appendChild(styleElement);
    }
    styleElement.innerHTML = `
    #${myId} { &
      ${css}
    }
    `;
    cssCode = css_beautify(css);
  }
  console.log('Got css',css)


  onMount(() => showCode());
  let mainEl : HTMLElement;
  let outerEl : HTMLElement;
</script>

<svelte:head>
  {@html github}   
</svelte:head>

<div class="two-column" bind:this={outerEl}>
  <div class="main-container" 
    id={myId}
  >
    <main            
      bind:this={mainEl}
      class:highlight={$outlineMode}
      class:landscape={aspect == "L"}
      class:potrait={aspect != "L"}
    >
      <slot />
    </main>
    <button on:click={() => ($outlineMode = !$outlineMode)}>
      {#if !$outlineMode}
        Outline divs
      {:else}
        Remove outlines
      {/if}
    </button>
    <slot name="instructions" />
  </div>
  <div class="code-box">
    {#if !htmlCode}<button on:click={showCode}>Show Code</button>{/if}
    <div class="code">
      <h3>HTML</h3>
      <HighlightAuto code={htmlCode} />
      <h3>CSS</h3>
      <HighlightAuto code={cssCode} />
    </div>
  </div>
</div>

<style>
  .code-box {
    max-width: 50%;
  }
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
