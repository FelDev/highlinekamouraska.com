<script>
  import { TabsTransition } from "@roxi/routify/decorators";
  import { writable } from "svelte/store";
  import BottomNav from "./_components/BottomNav.svelte";
  import { url, isActive } from "@roxi/routify";
  
  const width = writable();
  const color = writable();
  const _urls = [
    ["./accueil", "🏠", "#FF6500"],
    ["./festival", "Festival", "#70C79E"],
    ["./retraite", "Retraites", "#70C79E"],
    ["./historique", "Historique", "#70C79E"],
    ["./equipe", "L'équipe", "#70C79E"],
  ];
  $: urls = _urls.map(([path, name, color]) => ({
    name,
    href: $url(path),
    color,
    active: !!$isActive(path)
  }));
  
  // $: urlOrder = urls.map(({href}) => href);
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
  div.inset {
    bottom: 64px;
    overflow: hidden;
  }

</style>
<div style="height: 100%">

  <div class="inset" bind:offsetWidth={$width}>
    <slot decorator={TabsTransition} scoped={{ width }} />
  </div>
  <BottomNav {urls} height="64px" />
</div>
