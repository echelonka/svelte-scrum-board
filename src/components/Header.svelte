<script>
  import {fade, fly} from 'svelte/transition'

  let headerVisible = false

  setTimeout(() => headerVisible = true, 0)
</script>

<style>
  h1 {
    font-family: 'Overpass', sans-serif;
    font-weight: bold;
    letter-spacing: 0.12em;
  }
</style>

<section class="hero">
  <div class="hero-body">
    {#if headerVisible}
      <div class="container is-flex">
        <img src="/assets/images/svelte-logo.svg" alt="logo" width="50" style="margin-right: 20px" in:fly="{{y: -20, duration: 500}}">
        <h1 class="is-uppercase is-size-2">
          {#each 'Svelte board' as char, i}
            <span in:fade={{delay: 500 + i * 100, duration: 200}}>{char}</span>
          {/each}
        </h1>
      </div>
    {/if}
  </div>
</section>