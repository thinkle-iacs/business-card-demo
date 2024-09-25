<script lang="ts">
  import img from "../assets/Surveyor.png";
  import BusinessCard from "../lib/BusinessCard.svelte";
  import Instructions from "../lib/Instructions.svelte";
  import Tutorial from "../lib/Tutorial.svelte";
</script>

<Tutorial steps={3}>
  <span slot="title">Corners Example</span>
  <img slot="target" style="width:3.5in" src={img} />
  <div slot="steps">
    <div>
      <BusinessCard
        css={`
          main {
            font-family: Georgia, serif;
            background-color: #283423;
            color: #d9f1c2;
          }
          .logo {
            /* Placeholder styling */
          }
          .name-title {
            font-size: 20pt;
            font-weight: bold;
            font-family: Futura, sans-serif;
          }
          .description {
            font-size: 12pt;
          }
          .contact-info {
            font-size: 8pt;
          }
        `}
      >
        <div class="logo">
          CAM<br />ERA
        </div>
        <div>
          <div class="name-title">Fran Vanzant</div>
          <div class="description">Building Surveyor</div>
        </div>
        <div class="contact-info">
          <div>(311) 555-0199</div>
          <div>Fran@buildingsurveys.com</div>
        </div>
        <div slot="instructions">
          <Instructions>
            <ul>
              <li>Put in placeholder text for the image</li>
              <li>
                Break the card into 3 elements:
                <ol>
                  <li>Camera image</li>
                  <li>Title/Description</li>
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
            justify-content: space-between;
            box-sizing: border-box;
            padding: 8pt;
            font-family: Georgia, serif;
            background-color: #283423;
            color: #d9f1c2;
          }
          .logo {
          }
          .name-title {
            font-size: 20pt;
            font-weight: bold;
            font-family: Futura, sans-serif;
          }
          .description {
            font-size: 12pt;
          }
          .contact-info {
            font-size: 8pt;
          }
        `}
      >
        <div class="logo">
          CAM<br />ERA
        </div>
        <div>
          <div class="name-title">Fran Vanzant</div>
          <div class="description">Building Surveyor</div>
        </div>
        <div class="contact-info">
          <div>(311) 555-0199</div>
          <div>Fran@buildingsurveys.com</div>
        </div>
        <div slot="instructions">
          <Instructions>
            <ul>
              <li>
                Add <code>display: flex</code> and
                <code>flex-direction:column</code> to lay out elements vertically
              </li>
              <li>
                Add <code>justify-content: space-between;</code> to spread items
                out.
              </li>
              <li>
                Add <code>padding:8pt;</code> to the whole card to put space
                around the edges (+<code>box-sizing:border-box;</code> to prevent
                the card from growing)
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
            border-radius: 16pt;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            box-sizing: border-box;
            padding: 16pt;
            font-family: Georgia, serif;
            background-color: #283423;
            color: #d9f1c2;
          }
          .logo {
            height: 40pt;
            align-self: end;
          }
          .name-title {
            font-size: 20pt;
            font-weight: bold;
            font-family: Futura, sans-serif;
          }
          .description {
            font-size: 12pt;
          }
          .contact-info {
            height: 40pt;
            font-size: 8pt;
            display: flex;
            flex-direction: column;
            justify-content: end;
          }
        `}
      >
        <div class="logo">
          CAM<br />ERA
        </div>
        <div>
          <div class="name-title">Fran Vanzant</div>
          <div class="description">Building Surveyor</div>
        </div>
        <div class="contact-info">
          <div>(311) 555-0199</div>
          <div>Fran@buildingsurveys.com</div>
        </div>
        <div slot="instructions">
          <Instructions>
            <ul>
              <li>
                Add <code>align-self: end;</code> to the camera div to move it to
                the right.
              </li>
              <li>
                Set the height on the top and bottom elements to be equal so
                that our middle element is centered.
                <ul>
                  <li><code>height:40pt;</code></li>
                  <li><code>display:flex;flex-direction:column;</code></li>
                  <li>
                    For the bottom element, move text to the end with: <code
                      >justify-content: end</code
                    >
                  </li>
                </ul>
              </li>
              <li>
                Throw a <code>border-radius</code> on to match our "rounded" look
              </li>
            </ul>
          </Instructions>
        </div>
      </BusinessCard>
    </div>
  </div>
</Tutorial>

