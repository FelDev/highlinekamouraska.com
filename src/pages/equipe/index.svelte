<script >
  import { url, layout } from "@roxi/routify";
  import marked from "marked";

  const posts = $layout.parent.children
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
    align-items: flex-start;
    justify-content: space-around;
  }
  li {
    list-style: none;
    min-width: 15rem;
    max-width: 30rem;
    border: .1rem solid black;
    border-radius: 1rem;
    padding: 1rem;
    margin: 0 2rem;
  }
</style>



  <br />
  <h1>L'équipe</h1>
  <p>Nos belles grosses faces.</p>
  <ul class="posts">
    {#each posts as {meta, path}}
      <li class="card"> 
        <img src="{meta.frontmatter.thumbnail}" alt="">
        <h2>{meta.frontmatter.name}</h2>
        <p>{@html marked(meta.frontmatter.bio)}</p>
      </li>
      
      <!-- <li class="card"> 
        <a class="title" href={$url(path)}>{meta.frontmatter.name}</a>
        {@html marked(meta.frontmatter.name)}
      </li> -->
    {/each}
  </ul>





