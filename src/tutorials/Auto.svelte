<script lang="ts">
  import img from "../assets/Auto.png";
  import BusinessCard from "../lib/BusinessCard.svelte";
  import Instructions from "../lib/Instructions.svelte";
  import Tutorial from "../lib/Tutorial.svelte";
</script>

<Tutorial steps={4}>
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
        <div slot="instructions">
          <Instructions>
            <ul>
              <li>Break the card into 3 sections and wrap each in a div</li>
              <li>Put in placeholder text for the images</li>
              <li>
                Use <code>flex-direction: column</code> and
                <code>justify-content: space-between</code> to make the card fill
                up the vertical space
              </li>
            </ul>
          </Instructions>
        </div>
      </BusinessCard>
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
        <div slot="instructions">
          <Instructions>
            <ul>
              <li>
                Use <code>display: flex</code> to make the bottom section go left-to-right
              </li>
              <li>
                Use
                <code>justify-content: space-between</code> to spread out the items
                in the bottom section
              </li>
              <li>
                Adjust font sizes with <code>font-size</code> and center the top
                text with
                <code>text-align: center</code>
              </li>
            </ul>
          </Instructions>
        </div>
      </BusinessCard>
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
          <div style="visibility:hidden;padding-left:8pt;">QR</div>
          <div>CAR<br />IMG</div>
          <div style="padding-right:8pt;">QR</div>
        </div>
        <div
          style="display: flex; justify-content: space-between; font-size:7pt"
        >
          <div>113 Penn Lane, Dorin, CO</div>
          <div>311-555-0146</div>
          <div>emilio@auto.site.com</div>
        </div>
        <div slot="instructions">
          <Instructions>
            <ul>
              <li>
                Use <code>justify-content: space-between</code> to center the car
                and QR code
              </li>
              <li>
                Create a second invisible QR code to allow the centering to work
                perfectly (use <code>visibility: hidden</code> to hide the second
                code)
              </li>
              <li>Add a little padding to QR codes to space out from edge</li>
            </ul>
          </Instructions>
        </div>
      </BusinessCard>
    </div>
    <div>
      <BusinessCard
        style="display:flex; flex-direction: column;
      justify-content: space-between; background-color: #E2CDA7; font-weight: bold;"
      >
        <div
          style="text-align: center; padding-top: 16px;
          font-variant: small-caps; font-family: sans-serif;
        "
        >
          <div style="font-size: 24pt; color: #2A4261;">Bandwick</div>
          <div style="font-size: 10pt; color: #c36946;">Auto Repairs</div>
        </div>
        <div
          style="display: flex; justify-content: space-between; align-items: end"
        >
          <div style="visibility:hidden;padding-left:8pt;">QR</div>
          <div>CAR<br />IMG</div>
          <div style="padding-right:8pt;">QR</div>
        </div>
        <div
          style="display: flex; justify-content: space-between; align-items: center; font-size:6pt;
          background-color: #413929; color: #E2CDA7; padding-left: 8px; padding-right: 8px;"
        >
          <div style="padding: 8px;">113 Penn Lane, Dorin, CO</div>
          <div
            style="padding: 8px; border-left: 1px solid #E2CDA7; border-right: 1px solid #E2CDA7;"
          >
            311-555-0146
          </div>
          <div style="padding: 8px;">emilio@auto.site.com</div>
        </div>
        <div slot="instructions">
          <Instructions>
            <ul>
              <li>Adjust color and typography.</li>
              <li>
                Add <code>border-left: 1px solid white;</code> and
                <code>border-right: 1px solid white;</code>
                to phone number to create separating lines
              </li>
              <li>
                Tweak font-size and padding on bottom items until it looks
                right.
              </li>
            </ul>
          </Instructions>
        </div>
      </BusinessCard>
    </div>
  </span>
</Tutorial>
