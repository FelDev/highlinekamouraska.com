<script context="module">
  export function getCMSData(layout, path) {
    let data = {};
    layout
      .children.filter(c => c.path === "/cms")[0]
      .children.filter(c => c.path === `/cms/${path}`)[0]
      .children.forEach(d => {
        data[d.meta.frontmatter.cmsID] = d.meta.frontmatter
      })
  return data
  // Used to do it like this with a single file per folder.
  //  return layout
      // .children.filter(c => c.path === "/cms")[0]
      // .children.filter(c => c.path === `/cms/${path}`)[0]
      // .children[0].meta.frontmatter
  }
</script>