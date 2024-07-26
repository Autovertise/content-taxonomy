<script>
  import contentTaxonomy from "$lib/json/content-taxonomy-2-2-nested.json";
  import ContentTaxonomyList from "../lib/components/ContentTaxonomyList.svelte";
</script>

<h1>Content Taxonomy 2.2</h1>
<ContentTaxonomyList {contentTaxonomy} />
