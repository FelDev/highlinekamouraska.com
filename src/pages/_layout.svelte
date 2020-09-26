<script>
  import { TabsTransition } from "@roxi/routify/decorators";
  import { writable } from "svelte/store";
  import BottomNav from "./_components/BottomNav.svelte";
  import { url, isActive } from "@roxi/routify";
  
  const width = writable();
  const color = writable();
  const _urls = [
    ["./accueil", "🏠", "#FF6500"],
    ["./festival", "Festival", "#8FD5DB"],
    ["./retraite", "Retraites", "#A1FAC3"],
    ["./historique", "Historique", "#0bF5CC"],
    ["./equipe", "L'équipe", "#88F0d0"],
  ];
  $: urls = _urls.map(([path, name, color]) => ({
    name,
    href: $url(path),
    color,
    active: !!$isActive(path)
  }));
  
  $: urlOrder = urls.map(({href}) => href);
</script>

<style>
  :global(body) {
    padding: 0;
  }
  * :global(.inset) {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
  }
  main.inset {
    bottom: 64px;
    overflow: hidden;
  }
  * :global(*) {
    text-align: center;
  }
  a {
    position: fixed;
    top: 0;
    left: 0;
    padding: 8px 16px;
    background: #555;
    color: white;
  }
</style>
<div style="height: 100%">

  <div class="inset" bind:offsetWidth={$width}>
    <slot decorator={TabsTransition} scoped={{ width }} />
  </div>
  <BottomNav {urls} height="64px" />
</div>
