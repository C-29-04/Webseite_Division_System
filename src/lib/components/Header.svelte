<script>
  import { page } from '$app/stores';
  
  let isMenuOpen = false;
  
  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }
  
  function closeMenu() {
    isMenuOpen = false;
  }
</script>

<header class="fixed top-0 left-0 right-0 z-50 bg-black/90 backdrop-blur-sm border-b border-gray-700/30">
  <nav class="container-custom">
    <div class="flex items-center justify-between h-16">
      <!-- Logo -->
      <a href="/" class="flex items-center space-x-2">
        <span class="text-xl font-bold text-white">DIVISION SYSTEM</span>
      </a>
      
      <!-- Desktop Navigation -->
      <div class="hidden md:flex items-center space-x-8">
        <a 
          href="/" 
          class="text-gray-300 hover:text-white transition-colors {$page.url.pathname === '/' ? 'text-white' : ''}"
        >
          Home
        </a>
        <a 
          href="/kontakt" 
          class="text-gray-300 hover:text-white transition-colors {$page.url.pathname === '/kontakt' ? 'text-white' : ''}"
        >
          Kontakt
        </a>
      </div>
      
      <!-- Mobile Menu Button -->
      <button 
        class="md:hidden flex flex-col justify-center items-center w-8 h-8 space-y-1.5 focus:outline-none"
        onclick={toggleMenu}
        aria-label="Toggle menu"
      >
        <span class="block w-6 h-0.5 bg-gray-300 transition-transform {isMenuOpen ? 'rotate-45 translate-y-2' : ''}"></span>
        <span class="block w-6 h-0.5 bg-gray-300 transition-opacity {isMenuOpen ? 'opacity-0' : ''}"></span>
        <span class="block w-6 h-0.5 bg-gray-300 transition-transform {isMenuOpen ? '-rotate-45 -translate-y-2' : ''}"></span>
      </button>
    </div>
    
    <!-- Mobile Menu -->
    {#if isMenuOpen}
      <div class="md:hidden absolute top-16 left-0 right-0 bg-black/90 backdrop-blur-sm border-b border-gray-700/30">
        <div class="px-4 py-4 space-y-3">
          <a 
            href="/" 
            class="block py-2 text-gray-300 hover:text-white transition-colors {$page.url.pathname === '/' ? 'text-white' : ''}"
            onclick={closeMenu}
          >
            Home
          </a>
          <a 
            href="/kontakt" 
            class="block py-2 text-gray-300 hover:text-white transition-colors {$page.url.pathname === '/kontakt' ? 'text-white' : ''}"
            onclick={closeMenu}
          >
            Kontakt
          </a>
        </div>
      </div>
    {/if}
  </nav>
</header>
