<script>
  import { layout } from "@roxi/routify";
  import marked from "marked";
  import { getCMSData } from "./_components/GetCMSData.svelte"
  const cmsData = getCMSData($layout, "festival")
  console.log('@cmsData: ', cmsData);
  
</script>
<style>
  /* #DELETE? not sure why this was not in global.css everywhere from the beginning */
  /* main { */
    /* background: #8fD5Db; */
    /* height: 100%; */
    /* overflow: auto; */
  /* } */
  :global(.important-links p) {
    text-align: center;
    font-size: 2rem;
  }

  .a-savoir {
    text-align: center;
  }
  .a-savoir div {
    text-align: center;
    padding-left: 7rem;
    position: relative;
    margin-bottom: 4rem;
  }
  .a-savoir h3 {
    text-align: left;
    margin-bottom: 0;
  }
  .a-savoir svg {
    position: absolute;
    top: 0;
    left: 0;
    height: 5rem;
    filter: drop-shadow(0.5rem 0.5rem 0.5rem rgba(24, 20, 3, 0.99));
    fill: aliceblue;
    fill: #AD9BAA;
    fill: #A4B0F5;
    /* fill: #177E89; */
    fill: #FFC857;

  }

  .cestQuoi {
    font-size: 5rem;
    display: flex;
    justify-content: center;
    align-items: center;
    max-width: 98vw;
  }
  .cestQuoi img {
    width: 33%;
    margin: 1rem;
    align-self: baseline;
  }
  @media screen and (max-width: 768px) {
    .cestQuoi {
      flex-direction: column;
    }
    .cestQuoi img {
      width: 45%;
      align-self: center;
    }
  
  }


</style>

<!-- routify:options index=1 -->
<main>
  <h1 id="svgLineTitle">
    <svg viewBox="0 0 500 100" fill="none">
      <path id="curve" d="M-2 5C265 163 531 2 531 -20" stroke="#70c79e" stroke-width="1.5" />
      <text width="500">
        <textPath xlink:href="#curve" fill="#151515" startOffset="22%">
          {cmsData.title}
        </textPath>
      </text>
    </svg>
  </h1> 
  
  
  <section class="content">
    <section class="important-links">
      {@html marked(cmsData.importantLinks)}
    </section>

    {@html marked(cmsData.cestQuoi)}
    <section class="cestQuoi">
      <img alt="Un bonhomme sur une highline" src="/images/quoi_1.png" loading="lazy"/>
      +
      <img alt="Une tente de camping" src="/images/quoi_2.png" loading="lazy"/>
      +
      <img alt="Des bonhommes qui socialisent" src="/images/quoi_3.png" loading="lazy"/>
    </section>

    <section class="a-savoir">
      <h2>Choses à savoir</h2>

      <!-- Font Awesome Free 5.15.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free (Icons: CC BY 4.0, Fonts: SIL OFL 1.1, Code: MIT License) -->
      <div>
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><!-- Font Awesome Free 5.15.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free (Icons: CC BY 4.0, Fonts: SIL OFL 1.1, Code: MIT License) --><path d="M434.027 26.329l-168 28C254.693 56.218 256 67.8 256 72h-58.332C208.353 36.108 181.446 0 144 0c-39.435 0-66.368 39.676-52.228 76.203-52.039 13.051-75.381 54.213-90.049 90.884-4.923 12.307 1.063 26.274 13.37 31.197 12.317 4.926 26.279-1.075 31.196-13.37C75.058 112.99 106.964 120 168 120v27.076c-41.543 10.862-72 49.235-72 94.129V488c0 13.255 10.745 24 24 24h144c13.255 0 24-10.745 24-24V240c0-44.731-30.596-82.312-72-92.97V120h40c0 2.974-1.703 15.716 10.027 17.671l168 28C441.342 166.89 448 161.25 448 153.834V38.166c0-7.416-6.658-13.056-13.973-11.837zM144 72c-8.822 0-16-7.178-16-16s7.178-16 16-16 16 7.178 16 16-7.178 16-16 16z"/></svg>
        <h3>{cmsData.feuT}</h3> 
        <p>{cmsData.feuD}</p>
      </div>
        <div>
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><!-- Font Awesome Free 5.15.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free (Icons: CC BY 4.0, Fonts: SIL OFL 1.1, Code: MIT License) --><path d="M32 464a48 48 0 0 0 48 48h288a48 48 0 0 0 48-48V128H32zm272-256a16 16 0 0 1 32 0v224a16 16 0 0 1-32 0zm-96 0a16 16 0 0 1 32 0v224a16 16 0 0 1-32 0zm-96 0a16 16 0 0 1 32 0v224a16 16 0 0 1-32 0zM432 32H312l-9.4-18.7A24 24 0 0 0 281.1 0H166.8a23.72 23.72 0 0 0-21.4 13.3L136 32H16A16 16 0 0 0 0 48v32a16 16 0 0 0 16 16h416a16 16 0 0 0 16-16V48a16 16 0 0 0-16-16z"/></svg>
          <h3>{cmsData.dechetT}</h3>
            <p>{cmsData.dechetD}</p>
      </div>
      <div>
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><!-- Font Awesome Free 5.15.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free (Icons: CC BY 4.0, Fonts: SIL OFL 1.1, Code: MIT License) --><path d="M400 32H48C21.5 32 0 53.5 0 80v352c0 26.5 21.5 48 48 48h352c26.5 0 48-21.5 48-48V80c0-26.5-21.5-48-48-48zM240 320h-48v48c0 8.8-7.2 16-16 16h-32c-8.8 0-16-7.2-16-16V144c0-8.8 7.2-16 16-16h96c52.9 0 96 43.1 96 96s-43.1 96-96 96zm0-128h-48v64h48c17.6 0 32-14.4 32-32s-14.4-32-32-32z"/></svg>
        <h3>{cmsData.parkingT}</h3>
        <p>{cmsData.parkingD}</p>
      </div>
      <div>
        <svg version="1.1" viewBox="0 0 576 512" xmlns="http://www.w3.org/2000/svg"><path d="m572.52 241.4c-54.23-105.81-161.59-177.4-284.52-177.4s-230.32 71.64-284.52 177.41c-4.6393 9.177-4.6393 20.013 0 29.19 54.23 105.81 161.59 177.4 284.52 177.4s230.32-71.64 284.52-177.41c4.6393-9.177 4.6393-20.013 0-29.19zm-284.52 158.6c-58.242 0-110.75-35.085-133.04-88.893-22.287-53.808-9.964-115.74 31.219-156.93s103.12-53.507 156.93-31.219c53.808 22.287 88.893 74.795 88.893 133.04 0.0387 79.545-64.455 144.04-144 144zm0-240c-8.5687 0.11975 26.603-4.2684-25.31 3.79-39.112 14.478-51.422 29.165-66.9 66.9-6.7166 46.928 4.9599 81.743 39.075 104.63 34.115 22.885 79.024 21.462 111.63-3.5324 32.603-24.994 45.64-67.994 32.399-106.88-13.241-38.888-49.81-65.001-90.892-64.905z"/></svg>
        <h3>{cmsData.securiteT}</h3>
        <p>{cmsData.securiteD}</p>
      </div>
      <div>
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512"><!-- Font Awesome Free 5.15.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free (Icons: CC BY 4.0, Fonts: SIL OFL 1.1, Code: MIT License) --><path d="M546.2 9.7c-5.6-12.5-21.6-13-28.3-1.2C486.9 62.4 431.4 96 368 96h-80C182 96 96 182 96 288c0 7 .8 13.7 1.5 20.5C161.3 262.8 253.4 224 384 224c8.8 0 16 7.2 16 16s-7.2 16-16 16C132.6 256 26 410.1 2.4 468c-6.6 16.3 1.2 34.9 17.5 41.6 16.4 6.8 35-1.1 41.8-17.3 1.5-3.6 20.9-47.9 71.9-90.6 32.4 43.9 94 85.8 174.9 77.2C465.5 467.5 576 326.7 576 154.3c0-50.2-10.8-102.2-29.8-144.6z"/></svg>
        <h3>{cmsData.respectT}</h3>
        <p>{cmsData.respectD}</p>
      </div>
      <div>
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><!-- Font Awesome Free 5.15.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free (Icons: CC BY 4.0, Fonts: SIL OFL 1.1, Code: MIT License) --><path d="M256 416c114.9 0 208-93.1 208-208S370.9 0 256 0 48 93.1 48 208s93.1 208 208 208zM233.8 97.4V80.6c0-9.2 7.4-16.6 16.6-16.6h11.1c9.2 0 16.6 7.4 16.6 16.6v17c15.5.8 30.5 6.1 43 15.4 5.6 4.1 6.2 12.3 1.2 17.1L306 145.6c-3.8 3.7-9.5 3.8-14 1-5.4-3.4-11.4-5.1-17.8-5.1h-38.9c-9 0-16.3 8.2-16.3 18.3 0 8.2 5 15.5 12.1 17.6l62.3 18.7c25.7 7.7 43.7 32.4 43.7 60.1 0 34-26.4 61.5-59.1 62.4v16.8c0 9.2-7.4 16.6-16.6 16.6h-11.1c-9.2 0-16.6-7.4-16.6-16.6v-17c-15.5-.8-30.5-6.1-43-15.4-5.6-4.1-6.2-12.3-1.2-17.1l16.3-15.5c3.8-3.7 9.5-3.8 14-1 5.4 3.4 11.4 5.1 17.8 5.1h38.9c9 0 16.3-8.2 16.3-18.3 0-8.2-5-15.5-12.1-17.6l-62.3-18.7c-25.7-7.7-43.7-32.4-43.7-60.1.1-34 26.4-61.5 59.1-62.4zM480 352h-32.5c-19.6 26-44.6 47.7-73 64h63.8c5.3 0 9.6 3.6 9.6 8v16c0 4.4-4.3 8-9.6 8H73.6c-5.3 0-9.6-3.6-9.6-8v-16c0-4.4 4.3-8 9.6-8h63.8c-28.4-16.3-53.3-38-73-64H32c-17.7 0-32 14.3-32 32v96c0 17.7 14.3 32 32 32h448c17.7 0 32-14.3 32-32v-96c0-17.7-14.3-32-32-32z"/></svg>
        <h3>{cmsData.contributionT}</h3>
        <p>{cmsData.contributionD}</p>
      </div>
    </section>
    
    <h2>Quelques images...</h2>
    <div class="video-responsive">
      <iframe title="Vidéo: Highline Kamouraska - Drone Teaser" width="560" height="315" src="https://www.youtube.com/embed/GUISQGrUUAw" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    </div>
  </section>
  <!-- <h1>Le Festival</h1>
  <h2>C'est quoi un festival de highline?</h2>
  <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Perferendis necessitatibus ipsum harum. Maiores voluptate, tempora voluptatibus assumenda dicta voluptatum, omnis quasi iusto molestiae vitae a? Dolorem eaque repellat voluptates velit.</p>
  <h2>Choses à savoir</h2>
  <ul>
    <li>Ne pas faire de feux</li>
    <li>Ramener ses déchêts</li>
    <li>Être responsable de sa sécurité</li>
  </ul>
  <h2>
   Achète tes billets par là ↓ 
  </h2>
  <p>laruchequebec.com (right?)</p> -->
</main>
