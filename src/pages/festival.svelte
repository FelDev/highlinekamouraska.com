<script>
  import { layout } from "@roxi/routify";
  import marked from "marked";
  import { getCMSData } from "./_components/GetCMSData.svelte"
  const cmsData = getCMSData($layout, "festival")
  console.log('@cmsData: ', cmsData);
  
</script>
<style>
  main {
    background: #8fD5Db;
    height: 100%;
    overflow: auto;
  }
</style>

<!-- routify:options index=1 -->
<main>
  <br />
  <h1>{cmsData.title}</h1>
  <section class="content">
    {@html marked(cmsData.text)}
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
