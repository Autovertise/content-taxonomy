<script>
  import ContentTaxonomyListItem from "./ContentTaxonomyListItem.svelte";

  export let contentTaxonomy;
</script>

{#each contentTaxonomy as { id, name, scd, children }}
  <ContentTaxonomyListItem {id} {name} {scd} {children} />
{/each}
