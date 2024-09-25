<script lang="ts">
  import img from "../assets/Plumbing.png";
  import BusinessCard from "../lib/BusinessCard.svelte";
  import Instructions from "../lib/Instructions.svelte";
  import Tutorial from "../lib/Tutorial.svelte";
</script>

<Tutorial>
  <img slot="target" src={img} style="width:3.5in;" />
  <div slot="title">Bottom Left Example</div>
  <div slot="steps">
    <div class="step">
      <BusinessCard
        css={`
          main {
            font-family: sans-serif;
            background-color: #161d51;
            color: white;
          }
          .title {
            font-weight: bold;
            font-size: 13pt;
          }
          .contact-info {
            font-size: 8pt;
          }
          .motto {
            font-weight: bold;
          }
        `}
      >
        <div class="title">
          <div>Bowriker</div>
          <div>Plumbing</div>
        </div>
        <div class="contact-info">(311) 555-0113</div>
        <div class="contact-info">
          <div class="motto">Leave it to us</div>
          <div>bowrikerplumbing.site.com</div>
        </div>
        <div slot="instructions">
          <Instructions>
            <ul>
              <li>Group our three sections of content</li>
              <li>
                Adjust colors and typography with <code>background-color</code>,
                <code>color</code> and <code>font-size</code>
              </li>
            </ul>
          </Instructions>
        </div>
      </BusinessCard>
    </div>

    <div class="step">
      <BusinessCard
        css={`
          main {
            display: flex;
            flex-direction: column;
            justify-content: end;
            gap: 8pt;
            font-family: sans-serif;
            background-color: #161d51;
            color: white;
          }
          .title {
            font-weight: bold;
            font-size: 13pt;
          }
          .contact-info {
            font-size: 8pt;
          }
          .motto {
            font-weight: bold;
          }
        `}
      >
        <div class="title">
          <div>Bowriker</div>
          <div>Plumbing</div>
        </div>
        <div class="contact-info">(311) 555-0113</div>
        <div class="contact-info">
          <div class="motto">Leave it to us</div>
          <div>bowrikerplumbing.site.com</div>
        </div>
        <div slot="instructions">
          <Instructions>
            <ul>
              <li>
                Use <code>display:flex</code> +
                <code>flex-direction:column</code> to create a vertical flexbox
              </li>
              <li>
                Use <code>justify-content: end</code> to move items to the
                <i>end</i> of the box.
              </li>
              <li>
                Add <code>gap: 8pt;</code> to put a gap between our three groups.
              </li>
            </ul>
          </Instructions>
        </div>
      </BusinessCard>
    </div>

    <div class="step">
      <BusinessCard
        css={`
          main {
            padding: 16pt;
            border-radius: 16pt;
            box-sizing: border-box;
            display: flex;
            flex-direction: column;
            justify-content: end;
            gap: 8pt;
            font-family: sans-serif;
            background-color: #161d51;
            color: white;
          }
          .title {
            font-weight: bold;
            font-size: 13pt;
          }
          .contact-info {
            font-size: 8pt;
          }
          .motto {
            font-weight: bold;
          }
        `}
      >
        <div class="title">
          <div>Bowriker</div>
          <div>Plumbing</div>
        </div>
        <div class="contact-info">(311) 555-0113</div>
        <div class="contact-info">
          <div class="motto">Leave it to us</div>
          <div>bowrikerplumbing.site.com</div>
        </div>
        <div slot="instructions">
          <Instructions>
            <ul>
              <li>
                Add padding to the entire card to move content away from the
                edge with <code>padding: 16pt</code> (also add
                <code>box-sizing: border-box</code> to prevent the card from growing
                with the padding)
              </li>
              <li>
                Round the edges with <code>border-radius: 16pt</code>
              </li>
            </ul>
          </Instructions>
        </div>
      </BusinessCard>
    </div>
  </div>
</Tutorial>

