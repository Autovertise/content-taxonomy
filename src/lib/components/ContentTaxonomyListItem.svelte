<script>
  export let id;
  export let name;
  export let scd;
  export let children;

  let open = false;

  function handleClick() {
    open = !open;
  }
</script>

{#if children.length > 0}
  <div class="row">
    <button on:click={handleClick}>
      🌳 ({id}) {name}
      {#if scd}
        <span class="scd">SCD</span>
      {/if}
      <span>({children.length} items)</span>
    </button>
  </div>
  {#if open}
    <div class="children">
      {#each children as { id, name, scd, children }}
        <svelte:self {id} {name} {scd} {children} />
      {/each}
    </div>
  {/if}
{:else}
  <div class="row">
    🍀 ({id}) {name}
    {#if scd}
      <span class="scd">SCD</span>
    {/if}
  </div>
{/if}

<style>
  .row {
    margin-bottom: 2em;
  }
  .scd {
    color: red;
  }
  .children {
    margin-left: 10em;
  }
</style>
