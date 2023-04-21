<script lang="ts">
  import PolkaDotGroup from "./lib/PolkaDotGroup.svelte";

  $: groups = [1, 1, 1, 1, 1, 1];

  function addGroup() {
    groups = [...groups, 1];
  }
</script>

<main>
  <p>
    By <a
      href="https://github.com/BrilliantDeviation7"
      target="_blank"
      rel="noreferrer">BrilliantDeviation7</a
    >. See the
    <a
      href="https://github.com/BrilliantDeviation7/polka-dot-cipher"
      target="_blank"
      rel="noreferrer">repository</a
    >.
  </p>

  <div class="card">
    <button on:click={addGroup}>Add Polka Dot Group</button>
  </div>

  <div class="groups">
    {#each groups as group}
      <PolkaDotGroup />
    {/each}
  </div>
</main>

<style>
  .groups {
    display: flex;
    column-gap: 40px;
    width: screen;
    flex-wrap: wrap;
  }
  button {
    padding: 2em;
    will-change: filter;
    transition: filter 300ms;
  }
  button:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
</style>
