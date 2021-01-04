<!-- routify:options index=0 -->
<script>
  import { metatags } from '@roxi/routify'
  metatags.title = 'Highline Kamouraska'
  metatags.description = 'Le meilleur festival de highline au monde. (ok, ok midline là...)'

  import { layout, beforeUrlChange } from "@roxi/routify";
  import { getCMSData } from "./_components/GetCMSData.svelte"
  const cmsData = getCMSData($layout, "accueil")

  // import { prefetch } from '@roxi/routify'
  // prefetch('/images/hero_1.jpg');
	
  let images = document.getElementsByTagName('img');
  
  let timeout = setTimeout(() => {
    changeImage(0);
  }, 2500);

  function changeImage(i) {
    let nextI = i+1 === images.length ? 0 : i+1;
    images[i].classList.remove('visible');
    images[nextI].classList.add('visible');
    timeout = setTimeout(() => {
      changeImage(nextI)
    }, 5000);
  }

  $beforeUrlChange(() => {
    clearTimeout(timeout);
    return true;
})
</script>

<style>
  p { 
    text-align: center;
    text-shadow: 0 0 0.5rem #ffe198; 
    position: relative;
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
  
  img {
    opacity: 0;
    transition: 2s;
    position: absolute;
    top:0;
    left:0;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  img.visible {
    opacity: 1;
  }

  .objectPosition-right {
    object-position:right;
  }

</style>

<main>
  <br />
  <h1>{cmsData.title}</h1>
  <!-- <p>{cmsData.text}</p> -->
  
  <img 
    class="visible objectPosition-right"
    alt="" 
    src="/images/hero_1.jpg"
  />
  <img 
    alt="" 
    src="/images/hero_2.jpg"
  />
  <img 
    alt="" 
    src="/images/hero_3.jpg"
  />
  <img 
    alt="" 
    src="/images/hero_4.jpg"
  />
  <img 
    alt="" 
    src="/images/hero_5.jpg"
  />

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