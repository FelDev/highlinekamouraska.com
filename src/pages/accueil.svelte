<!-- routify:options index=0 -->
<script>
  import { metatags } from '@roxi/routify'
  metatags.title = 'Highline Kamouraska'
  metatags.description = 'Le meilleur festival de highline au monde. (ok, ok midline là...)'

  import { layout } from "@roxi/routify";
  import { getCMSData } from "./_components/GetCMSData.svelte"
  const cmsData = getCMSData($layout, "accueil")
</script>

<style>
  main {
    background: #7fc5bb;
    height: 100%;
    overflow: auto;
    background-image: url(/images/hero.jpg);
    background-position: right;
    background-size: cover;
  }
  p { 
    text-align: center;
    text-shadow: 0 0 0.5rem #ffe198; 
  }
  @media (max-width:500px) {
    h1 {
      margin-top: 0.1rem;
      margin-bottom: 0.25rem;
      margin: 0;
    }
  }
</style>

<main>
  <br />
  <h1>{cmsData.title}</h1>
  <p>{cmsData.text}</p>
  <!-- <h1>Highline Kamouraska</h1> -->
  <!-- <p>Le meilleur festival de tout les festivaux dans la cours à Élyme!!!</p> -->
  <!-- <img src="/images/hero.jpg" alt=""> -->
</main>


<!-- Desperate attempt at solving every possible edgecase caused by the dark mountains in hero.jpg -->
<!-- #hero {
  background-image: linear-gradient(33deg, #f6f0e0 0%, #eeebdc 100%);
}
<div id="hero">
  <h1>{cmsData.title}</h1>
</div> -->