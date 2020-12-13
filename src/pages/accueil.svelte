<!-- routify:options index=0 -->
<script>
  import { metatags } from '@roxi/routify'
  metatags.title = 'Highline Kamouraska'
  metatags.description = 'Le meilleur festival de highline au monde. (ok, ok midline là...)'

  import { layout } from "@roxi/routify";
  import { getCMSData } from "./_components/GetCMSData.svelte"
  const cmsData = getCMSData($layout, "accueil")

  import {fade} from 'svelte/transition'
  // import { prefetch } from '@roxi/routify'
  // prefetch('/images/hero_1.jpg');
  // prefetch('/images/hero_2.jpg');
  // prefetch('/images/hero_3.jpg');
  // prefetch('/images/hero_4.jpg');
  // prefetch('/images/hero_5.jpg');
	const carouselPhotos = [
		'/images/hero_1.jpg',
		'/images/hero_2.jpg',
		'/images/hero_3.jpg',
		'/images/hero_4.jpg',
		'/images/hero_5.jpg',
	]
	
	let index = 0
	
	setInterval(() => {
    index = (index + 1) % carouselPhotos.length
  }, 5000);

</script>

<style>
  main {
    /* background: #7fc5bb; */
    height: 100%;
    overflow: auto;
    background-image: url(/images/hero.jpg);
    background-position: right;
    background-size: cover;
  }
  p { 
    text-align: center;
    text-shadow: 0 0 0.5rem #ffe198; 
    /* position: relative; */
    /* z-index: 10; */
  }
  
  h1 {
    font-size: 7vw;
    text-shadow: 0 0 1rem #DDD;
    z-index: 10;
    position: relative;
  }
  @media (max-width:768px) {
    h1 {
      font-size: 5rem;
      margin-top: 0.1rem;
      margin-bottom: 0.25rem;
      margin: 0;
    }
  }

  .bg {
    position: absolute;
    top:0;
    left:0;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
</style>

<main>
  <br />
  <h1>{cmsData.title}</h1>
  <!-- <p>{cmsData.text}</p> -->
  {#each [carouselPhotos[index]] as src (index)}
    <img 
      class="bg" 
      transition:fade 
      alt="" 
      src="{src}"
    />	
  {/each}
  <!-- {#each [carouselPhotos[index]] as src (index)}
    <div 
      class="bg" 
      transition:fade 
      alt="" 
      style="background-image: url({src})"
    />	
  {/each} -->
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