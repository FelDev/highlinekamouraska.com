<script context="module">
  export function getCMSData(layout, path) {
    return layout.parent
      .children.filter(c => c.path === "/cms")[0]
      .children.filter(c => c.path === `/cms/${path}`)[0]
      .children[0].meta.frontmatter
  }
</script>