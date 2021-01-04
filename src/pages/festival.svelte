<script>
  import { layout } from "@roxi/routify";
  import marked from "marked";
  import { getCMSData } from "./_components/GetCMSData.svelte"
  const cmsData = getCMSData($layout, "festival")
  console.log('@cmsData: ', cmsData);
  
</script>
<style>
  main {
    /* background: #8fD5Db; */
    height: 100%;
    overflow: auto;
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
  
  <!-- <h1>{cmsData.title}</h1> -->
  
  <section class="content">
    {@html marked(cmsData.text)}
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
