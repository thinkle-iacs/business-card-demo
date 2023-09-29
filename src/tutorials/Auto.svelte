<script lang="ts">
  import img from "../assets/Auto.png";
  import BusinessCard from "../lib/BusinessCard.svelte";
  import Instructions from "../lib/Instructions.svelte";
  import Tutorial from "../lib/Tutorial.svelte";
</script>

<Tutorial>
  <span slot="title">Top-Bottom Example</span>
  <img slot="target" style:width="3.5in" src={img} />
  <span slot="steps">
    <div>
      <BusinessCard
        style="display:flex; flex-direction: column;
      justify-content: space-between;"
      >
        <div>
          <div>Bandwick</div>
          <div>Auto Repairs</div>
        </div>
        <div>
          <div>CAR<br />IMG</div>
          <div>QR</div>
        </div>
        <div>
          <div>113 Penn Lane, Dorin, CO</div>
          <div>311-555-0146</div>
          <div>emilio@auto.site.com</div>
        </div>
      </BusinessCard>
      <Instructions>
        <ul>
          <li>Break the card into 3 sections and wrap each in a div</li>
          <li>Put in placeholder text for now for the images</li>
          <li>
            Use <code>flex-direction: column</code> and
            <code>justify-content: space-between</code> to make the card fill up
            the vertical space
          </li>
        </ul>
      </Instructions>
    </div>
    <div>
      <BusinessCard
        style="display:flex; flex-direction: column;
      justify-content: space-between;"
      >
        <div style="text-align: center;">
          <div>Bandwick</div>
          <div>Auto Repairs</div>
        </div>
        <div>
          <div>CAR<br />IMG</div>
          <div>QR</div>
        </div>
        <div
          style="display: flex; justify-content: space-between; font-size:7pt"
        >
          <div>113 Penn Lane, Dorin, CO</div>
          <div>311-555-0146</div>
          <div>emilio@auto.site.com</div>
        </div>
      </BusinessCard>
      <Instructions>
        <ul>
          <li>
            Use <code>display: flex</code> to make the bottom section go left-to-right
          </li>
          <li>
            Use
            <code>justify-content: space-between</code> to spread out the items in
            the bottom section
          </li>
          <li>
            Adjust font sizes with <code>font-size</code> and center the top
            text with
            <code>text-align: center</code>
          </li>
        </ul>
      </Instructions>
    </div>
    <div>
      <BusinessCard
        style="display:flex; flex-direction: column;
      justify-content: space-between;"
      >
        <div style="text-align: center;">
          <div>Bandwick</div>
          <div>Auto Repairs</div>
        </div>
        <div
          style="display: flex; justify-content: space-between; align-items: end"
        >
          <div style="visibility:hidden">QR</div>
          <div>CAR<br />IMG</div>
          <div>QR</div>
        </div>
        <div
          style="display: flex; justify-content: space-between; font-size:7pt"
        >
          <div>113 Penn Lane, Dorin, CO</div>
          <div>311-555-0146</div>
          <div>emilio@auto.site.com</div>
        </div>
      </BusinessCard>
      <Instructions>
        <ul>
          <li>
            Use <code>justify-content: space-between</code> to center the car and
            QR code
          </li>
          <li>
            Create a second invisible QR code to allow the centering to work
            perfectly (use <code>visibility: hidden</code> to hide the second code)
          </li>
        </ul>
      </Instructions>
    </div>
  </span>
</Tutorial>
