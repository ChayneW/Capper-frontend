<script>
  let menuOpen = false;
</script>

<nav class="bg-gray-800 p-4">
  <div class="container mx-auto flex justify-between items-center">
    <a href="/" class="text-white text-lg font-bold">My Svelte App</a>

    <!-- Mobile Menu Button -->
    <button class="text-white md:hidden" on:click={() => (menuOpen = !menuOpen)}>
      ☰
    </button>

    <!-- Desktop Menu -->
    <ul class="hidden md:flex space-x-4">
      <li><a href="/" class="text-white hover:text-gray-300">Home</a></li>
      <li><a href="/about" class="text-white hover:text-gray-300">About</a></li>
      <li><a href="/contact" class="text-white hover:text-gray-300">Contact</a></li>
    </ul>
  </div>

  <!-- Mobile Dropdown -->
  {#if menuOpen}
    <ul class="md:hidden mt-2 bg-gray-700 p-2">
      <li><a href="/" class="block text-white py-2">Home</a></li>
      <li><a href="/about" class="block text-white py-2">About</a></li>
      <li><a href="/contact" class="block text-white py-2">Contact</a></li>
    </ul>
  {/if}
</nav>
