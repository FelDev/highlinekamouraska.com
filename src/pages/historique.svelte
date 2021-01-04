<!-- routify:options index=3 -->
<script>
  import { fade, slide } from 'svelte/transition'
  let version = "short";
</script>
<style>
  /* main {
     #DELETE? not sure why this was not in global.css everywhere from the beginning 
    height: 100%;
    overflow: auto;
  } */

  #storyLengthButtons {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
  }

  /* #TODO: Actually implement nice custom radio buttons (not the example on W3schools...) */
  /* Customize the label (the container) */
  label {
    display: block;
    position: relative;
    padding: 0 35px;
    margin-bottom: 12px;
    cursor: pointer;
    font-size: 22px;
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
  }

  /* Hide the browser's default radio button */
  label input {
    position: absolute;
    opacity: 0;
    cursor: pointer;
    height: 0;
    width: 0;
  }

  /* Create a custom radio button */
  span {
    position: absolute;
    top: 0;
    left: 0;
    height: 25px;
    width: 25px;
    background-color: #eee;
    border-radius: 50%;
  }

  /* On mouse-over, add a grey background color */
  label:hover input ~ span {
    background-color: #ccc;
  }

  /* When the radio button is checked, add a blue background */
  label input:checked ~ span {
    background-color: #2196F3;
  }

  /* Create the indicator (the dot/circle - hidden when not checked) */
  span:after {
    content: "";
    position: absolute;
    display: none;
  }

  /* Show the indicator (dot/circle) when checked */
  label input:checked ~ span:after {
    display: block;
  }
  input:checked {
    border: 0.5rem solid #151515;
    border-radius: 0.5rem;
  }

  /* Style the indicator (dot/circle) */
  label span:after {
    top: 9px;
    left: 9px;
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: white;
  }

</style>

<main>  
  <h1 id="svgLineTitle">
    <svg viewBox="0 0 500 100" fill="none">
      <path id="curve" d="M-2 5C265 163 531 2 531 -20" stroke="#08d5b1" stroke-width="1.5" />
      <text width="500">
        <textPath xlink:href="#curve" fill="#151515" startOffset="23%">
          Historique
        </textPath>
      </text>
    </svg>
  </h1> 

  <!-- <h1>Historique</h1> -->

  <section class="content">
    <br>
    <div id="storyLengthButtons">
      <label>
        <input type=radio bind:group={version} value={"short"}>
        <span></span>
        Version courte
      </label>

      <label>
        <input type=radio bind:group={version} value={"long"}>
        <span></span>
        Version longue
      </label>
    </div>

    {#if version === "short"}
      <div id="short" in:fade={{ delay: 300, duration: 300 }} out:slide={{ duration: 300 }}>
        <p>Julien et Maxime cherchaient une place ou dormir finalement et tombèrent en amour.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
      </div>
    {:else}
      <div id="long" in:fade={{ delay: 300, duration: 300 }} out:slide={{ duration: 300 }}> 
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde sit libero qui vitae adipisci enim pariatur, doloremque nam repudiandae velit at ipsa? Vel officiis amet esse officia at dolores saepe.</p>
      </div>
    {/if}

  </section>
</main>
