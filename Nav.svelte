<script>
  import { onMount } from "svelte";
  let open = false;

  // Optional: close menu on route change or outside click - you can add later

  const toggleMenu = () => {
    open = !open;
  };
</script>

<nav class="bg-white shadow-md sticky top-0 z-50">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex justify-between h-16 items-center">
      <div class="flex-shrink-0 font-bold text-xl text-blue-600">Alexander Meade</div>

      <!-- Desktop Links -->
      <div class="hidden md:flex space-x-8">
        <a href="/" class="text-gray-700 hover:text-blue-600 font-semibold">Home</a>
        <a href="#projects" class="text-gray-700 hover:text-blue-600 font-semibold">Projects</a>
        <a href="#contact" class="text-gray-700 hover:text-blue-600 font-semibold">Contact</a>
      </div>

      <!-- Hamburger Menu Button -->
      <button 
        class="md:hidden inline-flex items-center justify-center p-2 rounded-md text-gray-700 hover:text-blue-600 focus:outline-none"
        aria-label="Toggle menu"
        on:click={toggleMenu}
      >
        <svg class="block h-6 w-6" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round">
          {#if !open}
            <path d="M4 6h16M4 12h16M4 18h16"></path>
          {:else}
            <path d="M6 18L18 6M6 6l12 12"></path>
          {/if}
        </svg>
      </button>
    </div>
  </div>

  <!-- Mobile Menu -->
  {#if open}
    <div class="md:hidden px-4 pb-4 space-y-1 border-t border-gray-200">
      <a href="/" class="block py-2 text-gray-700 hover:text-blue-600 font-semibold" on:click={() => open = false}>Home</a>
      <a href="#projects" class="block py-2 text-gray-700 hover:text-blue-600 font-semibold" on:click={() => open = false}>Projects</a>
      <a href="#contact" class="block py-2 text-gray-700 hover:text-blue-600 font-semibold" on:click={() => open = false}>Contact</a>
    </div>
  {/if}
</nav>

