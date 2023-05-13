<script lang="ts">
  import PolkaDotGroup from "./lib/PolkaDotGroup.svelte";
  import key from "./assets/key.json";

  let plaintext = "";

  function addGroup() {
    plaintext += "6";
  }
</script>

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

<button on:click={addGroup}>Add Polka Dot Group</button>
<input bind:value={plaintext} placeholder="Type plaintext here..." />

<div class="groups">
  {#each plaintext as char, i}
    {#if i < plaintext.length && Object.values(key).includes(char.toUpperCase())}
      <PolkaDotGroup inputCharacter={char} />
    {:else}
      <PolkaDotGroup inputCharacter={"6"} />
    {/if}
  {/each}
</div>

<style>
  .groups {
    display: flex;
    column-gap: 40px;
    width: screen;
    flex-wrap: wrap;
  }

  p {
    margin-top: 0;
    margin-bottom: 40px;
  }

  button {
    margin-bottom: 40px;
    display: block;
  }

  input {
    width: 50vw;
    font-size: 18px;
    padding: 10px;
    margin-bottom: 40px;
    border-radius: 8px;
    border: solid #e5e7eb 3px;
    transition: border-color 0.25s, filter 300ms;
  }
  input:hover {
    border-color: #646cff;
    filter: drop-shadow(0 0 20px #646cffaa);
  }
  input:focus,
  input:focus-visible {
    outline: 4px auto -webkit-focus-ring-color;
  }
</style>
