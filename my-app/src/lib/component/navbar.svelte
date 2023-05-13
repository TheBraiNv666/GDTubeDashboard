<script lang="ts">
  import { fade } from 'svelte/transition';

  let isOpen = false;
  let isMenuVisible = true;

  function goBack() {
    isOpen = false;
  }
</script>

<style>
  .navbar {
    font-family: "Uni Sans Demo", sans-serif;
    position: fixed;
    top: 0px;
    left: 0;
    width: 110px;
    height: 100vh;
    background-color: #131939;
    color: #fff;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
    cursor: pointer;
    z-index: 100;
    overflow: hidden;
    transition: width 0.3s ease-in-out;
  }

  .navbar:hover {
    width: 200px;
  }

  .navbar__item {
    font-size: 20px;
    margin-top: 20px;
    margin-bottom: 0;
    transition: transform 0.2s ease-in-out;
    color: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 50px;
    text-decoration: none;
  }

  .navbar__item__icon {
    margin-right: 10px;
  }

  .navbar__item:hover {
    transform: translateX(10px);
  }

  .navbar__item-enter {
    opacity: 0;
    transform: translateX(-20px);
  }

  .navbar__item-enter-active {
    opacity: 1;
    transform: translateX(0);
    transition: all 0.3s ease-in-out;
  }

  .navbar__item-exit {
    opacity: 1;
    transform: translateX(0);
  }

  .navbar__item-exit-active {
    opacity: 0;
    transform: translateX(-20px);
    transition: all 0.3s ease-in-out;
  }
</style>

{#if isMenuVisible}
  <div class="navbar">
    <div class="navbar__item" on:click={() => { isOpen = !isOpen }}>
      <span class="navbar__item__icon">☰</span> Menu
    </div>
  </div>
{/if}

{#if isOpen}
  <div class="navbar">
      <div class="navbar__item" on:click={goBack}>
        <span class="navbar__item__icon">↩</span> Retour
      </div>
      <a href="/gdtubehelp" class="navbar__item" transition:fade="{{ duration: 300 }}">GDTube</a>
      <a href="/gdprotecthelp" class="navbar__item" transition:fade="{{ duration: 500, delay: 100 }}">GDProtect</a>
      <a href="https://discord.gg/TvS8qHyFUW" class="navbar__item" transition:fade="{{ duration: 700, delay: 200 }}">Support</a>
  </div>
{/if}