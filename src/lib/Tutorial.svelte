<script>
  export let steps = 3;
  let active = 1;
  function prevStep() {
    if (active > 1) {
      active--;
    }
  }
  function nextStep() {
    if (active < steps) {
      active++;
    }
  }
</script>

<section>
  <h1>
    <slot name="title">Business Card Tutorial</slot>
  </h1>
  <div class="cols">
    <div>
      <slot name="target">Target</slot>
    </div>
    <div class="step-container">
      <div
        class="steps"
        class:active1={active == 1}
        class:active2={active == 2}
        class:active3={active == 3}
        class:active4={active == 4}
        class:active5={active == 5}
        class:active6={active == 6}
        class:active7={active == 7}
        class:active8={active == 8}
      >
        <slot name="steps">
          <div>
            <div>Step 1</div>
            <div>Step 2</div>
            <div>Step 3</div>
          </div>
        </slot>
      </div>
      <div class="player">
        <button disabled={active == 1} on:click={prevStep}>&lt; Back</button>
        <button disabled={active == steps} on:click={nextStep}>Next &gt;</button
        >
      </div>
    </div>
  </div>
</section>

<style>
  h1 {
    text-align: center;
  }
  .step-container {
    display: flex;
    flex-direction: column-reverse;
  }
  .player {
    margin-bottom: auto;
  }
  .cols {
    display: flex;
    justify-content: center;
    gap: 8px;
    align-items: top;
  }
  .steps > :global(*) > :global(*) {
    display: none;
  }
  .steps.active1 > :global(*) > :global(*:nth-child(1)) {
    display: block;
  }
  .steps.active2 > :global(*) > :global(*:nth-child(2)) {
    display: block;
  }
  .steps.active3 > :global(*) > :global(*:nth-child(3)) {
    display: block;
  }
  .steps.active4 > :global(*) > :global(*:nth-child(4)) {
    display: block;
  }
  .steps.active5 > :global(*) > :global(*:nth-child(5)) {
    display: block;
  }
  .steps.active6 > :global(*) > :global(*:nth-child(6)) {
    display: block;
  }
  .steps.active7 > :global(*) > :global(*:nth-child(7)) {
    display: block;
  }
  .steps.active8 > :global(*) > :global(*:nth-child(8)) {
    display: block;
  }
</style>
