<script >
  import { url, layout } from "@roxi/routify";
  import marked from "marked";

  const posts = $layout.children
    .filter((c) => c.meta["frontmatter"])
    .sort((a, b) => b.meta["frontmatter"].order < a.meta["frontmatter"].order ? 1 : -1);
  console.log('@posts: ', posts);
  
</script>
<style>
  img {
    max-width: 15rem;
    display: block;
    margin: auto;
    border-radius: 50%;

  }
  ul {
    display: flex;
    flex-wrap: wrap;
    padding: 0 2rem;
    /* align-items: flex-start; */
    justify-content: space-around;
  }
  li {
    background: #88F0D0;
    list-style: none;
    min-width: 25rem;
    max-width: 32rem;
    box-shadow: 0px 15px 25px -4px rgba(30,30,60,0.25);
    border-radius: 1rem;
    padding: 1rem;
    margin: 2rem;
    flex-grow: 1;
    box-shadow: 0rem 0rem 1.5rem 0.1rem green;
  }
</style>



<h1 id="svgLineTitle">
  <svg viewBox="0 0 500 100" fill="none">
    <path id="curve" d="M-2 5C265 163 531 2 531 -20" stroke="#08d5b1" stroke-width="1.5" />
    <text width="500">
      <textPath xlink:href="#curve" fill="#151515" startOffset="23%">
        L'équipe
      </textPath>
    </text>
  </svg>
</h1>
<ul class="posts">
  {#each posts as {meta, path}}
    <li class="card dark-bg">
      <img src="{meta.frontmatter.thumbnail}" alt="" width="150px" height="150px">
      <h2>{meta.frontmatter.name}</h2>
      <p>{@html marked(meta.frontmatter.bio)}</p>
    </li>
    
    <!-- <li class="card"> 
      <a class="title" href={$url(path)}>{meta.frontmatter.name}</a>
      {@html marked(meta.frontmatter.name)}
    </li> -->
  {/each}
</ul>
<section class="content">
  <p>On pourrais inclure des liens vers vos comptes instagram, twitter, etc...</p>
</section>
<br>




