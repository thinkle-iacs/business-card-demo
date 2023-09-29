<script lang="ts">
  import img from "../assets/Emilio.png";
  import BusinessCard from "../lib/BusinessCard.svelte";
  import Instructions from "../lib/Instructions.svelte";
  import Tutorial from "../lib/Tutorial.svelte";
</script>

<Tutorial>
  <span slot="title">Side-by-Side Example</span>
  <img slot="target" style:width="3.5in" src={img} />
  <span slot="steps">
    <div>
      <BusinessCard style="display:flex;">
        <div>
          <div>Emilio</div>
          <div>Carter</div>
        </div>
        <div>
          <div>Electrician</div>
          <div>311-555-0146</div>
          <div>emilio@electrian.site.com</div>
        </div>
      </BusinessCard>
      <Instructions>
        Wrap the two sections of the card (left and right) in two divs.
        <br />
        <br />Add <code>display:flex</code> to the main card to put the elements
        side by side
      </Instructions>
    </div>
    <div>
      <BusinessCard
        style="display:flex;
        justify-content: center;
        align-items: center;
      "
      >
        <div>
          <div>Emilio</div>
          <div>Carter</div>
        </div>
        <div>
          <div>Electrician</div>
          <div>311-555-0146</div>
          <div>emilio@electrian.site.com</div>
        </div>
      </BusinessCard>
      <Instructions>
        Center the items horizontally and vertically.
        <ul>
          <li>
            <code>justify-content: center;</code>
            to center the items horizontally
          </li>
          <li><code>align-items:center</code> to align them vertically.</li>
        </ul>
      </Instructions>
    </div>
    <div>
      <BusinessCard
        style="display:flex;
        justify-content: center;
        align-items: center;
        font-family: sans-serif;
        gap: 8pt;
      "
      >
        <div
          style="text-transform: uppercase; font-size: 26pt;
          padding-right: 8pt;
          border-right: 1px solid black;
        "
        >
          <div>Emilio</div>
          <div>Carter</div>
        </div>
        <div style="font-size: 8pt">
          <div style="text-transform: uppercase">Electrician</div>
          <div style="margin-top: 8pt">
            <div>311-555-0146</div>
            <div>emilio@electrian.site.com</div>
          </div>
        </div>
      </BusinessCard>
      <Instructions>
        Final touches now!
        <ul>
          <li>
            Add <code>border-right: 1px solid black</code> to the name div to create
            a vertical line
          </li>
          <li>
            Adjust the typography with <code>font-family</code>,
            <code>text-transform: uppercase</code>, and <code>font-size</code>.
          </li>
          <li>
            Add another sub-grouping to separate the word "Electrician" from the
            phone number and email
          </li>
          <li>
            Use the <code>gap</code> property
            <code>padding</code> and <code>margin</code> as needed to tweak our spacing
          </li>
        </ul>
      </Instructions>
    </div>
  </span>
</Tutorial>
