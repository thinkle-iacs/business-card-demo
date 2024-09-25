<script lang="ts">
  import img from "../assets/CabService.png";
  import BusinessCard from "../lib/BusinessCard.svelte";
  import Instructions from "../lib/Instructions.svelte";
  import Tutorial from "../lib/Tutorial.svelte";
</script>

<Tutorial steps={3}>
  <span slot="title">Top-Bottom Example</span>
  <img slot="target" style:width="3.5in" src={img} />
  <div slot="steps">
    <div>
      <BusinessCard
        css={`
          main {
            font-family: sans-serif;
            background-color: #EBD704;
          }
          .title {
            font-size: 16pt;
            font-weight: bold;
            font-family: cursive;
          }
          .description {
            font-size: 12pt;
            text-transform: uppercase;
          }
          .contact-info {
            font-size: 8pt;
          }
        `}
      >
        <div>
          CAB<br />IMG
        </div>
        <div>
          <div class="title">Sammy Kaur Cab Service</div>
          <div class="description">Atlanta Metropolitan Area</div>
        </div>
        <div>
          <hr />
        </div>
        <div class="contact-info">
          <div>+(311) 555-0199</div>
          <div>samkaurcabs.site.com</div>
        </div>
        <div slot="instructions">
          <Instructions>
            <ul>
              <li>Put in placeholder text for the image</li>
              <li>
                Break the card into 4 elements
                <ol>
                  <li>Cab image</li>
                  <li>Title/Description</li>
                  <li>Horizontal line (<code>&lt;hr&gt;</code>)</li>
                  <li>Contact info</li>
                </ol>
              </li>
              <li>Put some initial typography styling in</li>
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
            flex-direction: column;
            align-items: center;
            justify-content: center;
            font-family: sans-serif;
            background-color: #EBD704;
          }
          .title {
            font-size: 16pt;
            font-weight: bold;
            font-family: cursive;
          }
          .description {
            font-size: 10pt;
            text-transform: uppercase;
          }
          .contact-info {
            font-size: 8pt;
          }
          .hr-container {
            width: 1in;
          }
        `}
      >
        <div>
          CAB<br />IMG
        </div>
        <div>
          <div class="title">Sammy Kaur Cab Service</div>
          <div class="description">Atlanta Metropolitan Area</div>
        </div>
        <div class="hr-container">
          <hr />
        </div>
        <div class="contact-info">
          <div>+(311) 555-0199</div>
          <div>samkaurcabs.site.com</div>
        </div>
        <div slot="instructions">
          <Instructions>
            <ul>
              <li>
                Use <code>display:flex</code> and
                <code>flex-direction:column</code> to create a vertical flexbox for
                the page.
              </li>
              <li>
                Use <code>justify-content: center</code> to center vertically
              </li>
              <li>
                Use <code>align-items: center</code> to align items horizontally
              </li>
              <li>
                Add a <code>width: 1in</code> to the div with the
                <code>&lt;hr&gt;</code>
                to set its size.
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
            text-align: center;
            gap: 2pt;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            font-family: sans-serif;
            background-color: #EBD704;
          }
          .title {
            font-size: 16pt;
            font-weight: bold;
            font-family: cursive;
          }
          .description {
            font-size: 10pt;
            text-transform: uppercase;
          }
          .contact-info {
            font-size: 8pt;
          }
          .hr-container {
            width: 1in;
          }
          .hr-container hr {
            height: 2pt;
            border-style: solid;
            border-radius: 2pt;
            background-color: black;
          }
        `}
      >
        <div>
          CAB<br />IMG
        </div>
        <div>
          <div class="title">Sammy Kaur Cab Service</div>
          <div class="description">Atlanta Metropolitan Area</div>
        </div>
        <div class="hr-container">
          <hr />
        </div>
        <div class="contact-info">
          <div>+(311) 555-0199</div>
          <div>samkaurcabs.site.com</div>
        </div>
        <div slot="instructions">
          <Instructions>
            <ul>
              <li>
                Use <code>text-align: center</code> to center the text within all
                blocks.
              </li>
              <li>
                Use <code>gap:2pt</code> on the main flexbox to add a small gap between
                all groups on the page
              </li>
              <li>
                Adjust the style of the <code>&lt;hr&gt;</code> line with
                <code>height:2pt;</code> <code>border-style: solid;</code>
                <code>border-radius: 2pt;</code> and
                <code>background-color: black;</code>
              </li>
            </ul>
          </Instructions>
        </div>
      </BusinessCard>
    </div>
  </div>
</Tutorial>
