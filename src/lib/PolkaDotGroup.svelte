<script lang="ts">
  import key from "../assets/key.json";
  const status = [false, false, false, false, false];
  function handleClick(event) {
    let id = Number(event.target.id);
    status[id] = !status[id];
  }
</script>

<div class="container">
  <div class="left">
    <div id="0" class="dot" on:click={handleClick} class:active={status[0]} />
    <div id="1" class="dot" on:click={handleClick} class:active={status[1]} />
  </div>
  <div class="right">
    <div id="2" class="dot" on:click={handleClick} class:active={status[2]} />
    <div id="3" class="dot" on:click={handleClick} class:active={status[3]} />
    <div id="4" class="dot" on:click={handleClick} class:active={status[4]} />
  </div>
  <div style="margin-left: auto; margin-right: auto; font-size: 20px;">
    <!-- {status.map((e) => (e ? 1 : 0))} -->
    {key[status.map((e) => (e ? 1 : 0)).join("")]}
  </div>
</div>

<style>
  .container {
    position: relative;
    display: flex;
    flex-wrap: wrap;
    width: 90px;
  }

  .left {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .dot {
    height: 40px;
    width: 40px;
    border-radius: 50%;
    background-color: #f5f3f5;
    transition: background-color 0.3s ease, transform 0.3s ease;
    margin-top: 8px;
    cursor: pointer;
    border: 2px solid #1b264f;
  }

  .dot:hover {
    transform: scale(1.1);
  }

  .active {
    background-color: #1b264f;
  }
</style>
