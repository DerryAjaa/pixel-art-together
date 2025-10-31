<script>
  import logo from "../../static/logo.svg";
  import { onMount } from "svelte";

  let webShareSupported = false;

  onMount(() => {
    if (navigator.share) {
      webShareSupported = true;
    }
  });

  function useWebShare() {
    if (!webShareSupported) {
      return;
    }

    navigator.share({
      title: document.title,
      text: "Draw Pixel Art with me",
      url: window.location.href,
    });
  }
</script>

<header
  class="-z-10 flex justify-between border-b-2 border-gray-100 bg-white py-5 pl-4"
>
  <h1 class="flex items-center pt-0.5 pl-[1px]">
    <img alt="Pixel art together" src={logo} />
  </h1>
</header>

<style>
  header {
    height: var(--header-height);
  }

  .twitter-row {
    display: flex;
    justify-content: flex-end;
    align-items: center;
    padding: 0.5rem 1rem;
    background: white;
    border-bottom: 1px solid #f3f4f6; /* tailwind gray-100 */
  }

  .twitter-btn {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    background: #1DA1F2;
    color: white;
    padding: 0.4rem 0.75rem;
    border-radius: 0.375rem;
    border: none;
    font-weight: 600;
    cursor: pointer;
    text-decoration: none;
  }

  .twitter-btn:hover {
    filter: brightness(0.95);
  }

  .twitter-icon {
    width: 1rem;
    height: 1rem;
    display: inline-block;
  }

  /* small helper for screen-reader-only text */
  .sr-only {
    position: absolute;
    width: 1px;
    height: 1px;
    padding: 0;
    margin: -1px;
    overflow: hidden;
    clip: rect(0, 0, 0, 0);
    white-space: nowrap;
    border: 0;
  }
</style>

<div class="twitter-row" aria-hidden={false}>
  <a
    class="twitter-btn"
    href="https://x.com/i/communities/1984283478868074699"
    onclick="window.open('https://twitter.com/intent/tweet?text='+encodeURIComponent('SOLBLOCK the pixel art on pumpfun')+'&url='+encodeURIComponent(window.location.href), '_blank', 'noopener'); return false;"
    role="button"
    aria-label="Share and join the Pixel Art community on Twitter"
  >
    <svg class="twitter-icon" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true">
      <path d="M23 4.56c-.8.35-1.6.58-2.46.69a4.28 4.28 0 0 0 1.88-2.37 8.54 8.54 0 0 1-2.71 1.03 4.27 4.27 0 0 0-7.29 3.9A12.11 12.11 0 0 1 3.16 3.15a4.27 4.27 0 0 0 1.32 5.7 4.2 4.2 0 0 1-1.94-.54v.05a4.27 4.27 0 0 0 3.42 4.19 4.3 4.3 0 0 1-1.93.07 4.27 4.27 0 0 0 3.99 2.96A8.57 8.57 0 0 1 1.5 19.54 12.08 12.08 0 0 0 7 21c7.55 0 11.68-6.26 11.68-11.69v-.53A8.37 8.37 0 0 0 23 4.56z"/>
    </svg>
    <span>Twitter Community</span>
    <span class="sr-only">Share page and join the Pixel Art community on Twitter</span>
  </a>
<div class="twitter-row" aria-hidden={false}>
  <a
    class="twitter-btn"
    href="https://pump.fun/coin/DqrQdv2PCRbvo6QbddE9DAyFMZys9poMepSiq4Tmpump"
    target="_blank"
    rel="noopener noreferrer"
    role="link"
    aria-label="Open pump.fun in a new tab"
  >
    <svg class="twitter-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" aria-hidden="true" width="16" height="16" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
      <path d="M18 13v6a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/>
      <polyline points="15 3 21 3 21 9"/>
      <line x1="10" y1="14" x2="21" y2="3"/>
    </svg>
    <span>pump.fun</span>
    <span class="sr-only">Open pump.fun in a new tab</span>
  </a>
</div>
</div>
