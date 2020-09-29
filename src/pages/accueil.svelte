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
  }
</style>

<!-- routify:options index=0 -->
<main>
  <br />
  <section>
    <!-- <h1>Highline Kamouraska</h1> -->
    <!-- <p>Le meilleur festival de tout les festivaux dans la cours à Élyme!!!</p> -->
    <h1>{cmsData.title}</h1>
    <p>{cmsData.text}</p>
  </section>
  <!-- <img src="/images/hero.jpg" alt=""> -->
</main>