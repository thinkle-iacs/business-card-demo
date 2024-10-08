<script lang="ts">
  import img from "../assets/Emilio.png";
  import BusinessCard from "../lib/BusinessCard.svelte";
  import Instructions from "../lib/Instructions.svelte";
  import Tutorial from "../lib/Tutorial.svelte";
</script>

<Tutorial steps={4}>
  <span slot="title">Side-by-Side Example</span>
  <img slot="target" style:width="3.5in" src={img} />
  <span slot="steps">
    <div>
      <BusinessCard
        css={`
          main {
            display: flex;
            background-color: #fdc20b;
          }         
        `}
      >
        <div class="left">
          <div>Emilio</div>
          <div>Carter</div>
        </div>
        <div class="right">
          <div>Electrician</div>
          <div>311-555-0146</div>
          <div>emilio@electrian.site.com</div>
        </div>
        <div slot="instructions">
          <Instructions>
            Wrap the two sections of the card (left and right) in two divs.
            <br />
            <br />Add <code>display:flex</code> to the main card to put the elements
            side by side
          </Instructions>
        </div>
      </BusinessCard>
    </div>

    <div>
      <BusinessCard
        css={`
          main {
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: #fdc20b;
          }
        `}
      >
        <div class="left">
          <div>Emilio</div>
          <div>Carter</div>
        </div>
        <div class="right">
          <div>Electrician</div>
          <div>311-555-0146</div>
          <div>emilio@electrian.site.com</div>
        </div>
        <div slot="instructions">
          <Instructions>
            Center the items horizontally and vertically.
            <ul>
              <li>
                <code>justify-content: center;</code> to center the items horizontally
              </li>
              <li>
                <code>align-items:center</code> to align them vertically.
              </li>
            </ul>
          </Instructions>
        </div>
      </BusinessCard>
    </div>

    <div>
      <BusinessCard
        css={`
          main {
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: sans-serif;
            gap: 8pt;
            background-color: #fdc20b;
          }
          .name {
            text-transform: uppercase;
            font-size: 26pt;
            padding-right: 8pt;
            border-right: 1px solid black;
          }
          .contact-info {
            font-size: 8pt;
          }
          .contact-info .role {
            text-transform: uppercase;
          }
          .contact-info .details {
            margin-top: 8pt;
          }
        `}
      >
        <div class="name">
          <div>Emilio</div>
          <div>Carter</div>
        </div>
        <div class="contact-info">
          <div class="role">Electrician</div>
          <div class="details">
            <div>311-555-0146</div>
            <div>emilio@electrian.site.com</div>
          </div>
        </div>
        <div slot="instructions">
          <Instructions>
            <ul>
              <li>
                Add <code>border-right: 1px solid black</code> to the name div to
                create a vertical line
              </li>
              <li>
                Adjust the typography with <code>font-family</code>,
                <code>text-transform: uppercase</code>, and
                <code>font-size</code>.
              </li>
              <li>
                Add another sub-grouping to separate the word "Electrician" from
                the phone number and email
              </li>
              <li>
                Use the <code>gap</code> property, <code>padding</code>, and
                <code>margin</code> as needed to tweak our spacing
              </li>
            </ul>
          </Instructions>
        </div>
      </BusinessCard>
    </div>

    <div>
      <BusinessCard
        css={`
          main {
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: sans-serif;
            gap: 8pt;
            background-color: #fdc20b;
          }
          .name {
            text-transform: uppercase;
            font-size: 26pt;
            padding-right: 8pt;
            border-right: 1px solid black;
          }
          .contact-info {
            font-size: 8pt;
          }
          .contact-info .role {
            text-transform: uppercase;
          }
          .contact-info .details {
            margin-top: 8pt;
          }
          .lightning {
            position: relative;
          }
          .lightning-bolt {
            position: absolute;
            font-size: 10pt;
            top: 8pt;
            left: 5pt;
            filter: saturate(0);
          }
        `}
      >
        <div class="name">
          <div>
            Emili<span class="lightning"
              >o<span class="lightning-bolt">⚡</span></span
            >
          </div>
          <div>Carter</div>
        </div>
        <div class="contact-info">
          <div class="role">Electrician</div>
          <div class="details">
            <div>311-555-0146</div>
            <div>emilio@electrian.site.com</div>
          </div>
        </div>
        <div slot="instructions">
          <Instructions>
            Use shenanigans to get that lightning bolt in place!
            <ul>
              <li>
                Add <code><span /></code> to wrap around O and the lightning bolt
                inside it
              </li>
              <li>
                Make the outside span <code>position: relative</code> so it can contain
                the inner span
              </li>
              <li>
                Make the lightning bolt <code>position: absolute</code> so we
                can position it with <code>top:</code> and <code>left:</code>
              </li>
              <li>Adjust positioning</li>
              <li>
                Make the emoji black-and-white with <code
                  >filter: saturate(0)</code
                >
              </li>
            </ul>
          </Instructions>
        </div>
      </BusinessCard>
    </div>
  </span>
</Tutorial>

