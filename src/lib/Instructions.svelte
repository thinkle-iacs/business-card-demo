<section class="instructions">
  <div><slot /></div>
</section>

<style>
  div :global(code) {
    display: inline-block;
  }
  .instructions {
    display: flex;
    flex-direction: column;
    justify-content: start;
    overflow-y: auto;
    margin-bottom: 8px;
    padding: 2em;
    background-color: #ffea8a;
    color: #223;
    max-width: 32em;
  }
</style>
