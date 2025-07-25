<script>
  import { onMount } from 'svelte';
  
  let heroSection;
  
  onMount(() => {
    // Parallax effect on scroll
    const handleScroll = () => {
      if (heroSection) {
        const scrolled = window.scrollY;
        const rate = scrolled * -0.5;
        heroSection.style.transform = `translateY(${rate}px)`;
      }
    };
    
    window.addEventListener('scroll', handleScroll);
    
    return () => {
      window.removeEventListener('scroll', handleScroll);
    };
  });
</script>

<svelte:head>
  <title>Division System - Professionelle Lautsprecher-Vermietung</title>
  <meta name="description" content="Division System - Hochwertige Lautsprecher-Systeme für Ihre Veranstaltungen in Bielefeld und Umgebung." />
</svelte:head>

<!-- Hero Section -->
<section class="relative h-screen overflow-hidden">
  <div 
    bind:this={heroSection}
    class="absolute inset-0 z-0"
    style="background-image: url('/Calvin-Speaker-Stitch1.jpg'); background-size: cover; background-position: center; will-change: transform;"
  >
    <div class="absolute inset-0 bg-gradient-to-b from-[--color-gray-darker]/70 via-[--color-gray-darker]/50 to-[--color-gray-darker]"></div>
  </div>
  
  <div class="relative z-10 h-full flex items-center">
    <div class="container-custom">
      <div class="max-w-3xl">
        <h1 class="text-4xl md:text-6xl font-bold text-white mb-6 animate-fade-in">
          Division System
        </h1>
        <p class="text-xl md:text-2xl text-gray-300 mb-8 animate-fade-in-delay">
          Professionelle Lautsprecher-Systeme für unvergessliche Veranstaltungen
        </p>
        <div class="flex flex-col sm:flex-row gap-4 animate-fade-in-delay-2">
          <a 
            href="/kontakt" 
            class="inline-block px-8 py-3 bg-white text-[--color-gray-darker] font-semibold rounded hover:bg-gray-100 transition-colors text-center"
          >
            Jetzt anfragen
          </a>
          <a 
            href="#services" 
            class="inline-block px-8 py-3 border-2 border-white text-white font-semibold rounded hover:bg-white hover:text-[--color-gray-darker] transition-colors text-center"
          >
            Mehr erfahren
          </a>
        </div>
      </div>
    </div>
  </div>
  
  <!-- Scroll Indicator -->
  <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce">
    <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3"></path>
    </svg>
  </div>
</section>

<!-- Services Section -->
<section id="services" class="py-20 bg-[--color-gray-ral7016]">
  <div class="container-custom">
    <div class="text-center mb-12">
      <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">
        Unsere Leistungen
      </h2>
      <p class="text-gray-300 max-w-2xl mx-auto">
        Wir bieten professionelle Audio-Lösungen für Events jeder Größenordnung
      </p>
    </div>
    
    <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
      <div class="bg-[--color-gray-dark] p-8 rounded-lg hover:transform hover:scale-105 transition-transform">
        <h3 class="text-xl font-semibold text-white mb-4">Vermietung</h3>
        <p class="text-gray-400">
          Hochwertige Lautsprecher-Systeme für Konzerte, Festivals und private Veranstaltungen.
        </p>
      </div>
      
      <div class="bg-[--color-gray-dark] p-8 rounded-lg hover:transform hover:scale-105 transition-transform">
        <h3 class="text-xl font-semibold text-white mb-4">Beratung</h3>
        <p class="text-gray-400">
          Professionelle Beratung zur optimalen Audio-Lösung für Ihre Veranstaltung.
        </p>
      </div>
      
      <div class="bg-[--color-gray-dark] p-8 rounded-lg hover:transform hover:scale-105 transition-transform">
        <h3 class="text-xl font-semibold text-white mb-4">Service</h3>
        <p class="text-gray-400">
          Lieferung, Aufbau und technischer Support durch erfahrene Techniker.
        </p>
      </div>
    </div>
  </div>
</section>

<!-- CTA Section -->
<section class="py-20 bg-[--color-gray-darker]">
  <div class="container-custom text-center">
    <h2 class="text-3xl md:text-4xl font-bold text-white mb-6">
      Bereit für perfekten Sound?
    </h2>
    <p class="text-gray-300 text-lg mb-8 max-w-2xl mx-auto">
      Kontaktieren Sie uns für ein unverbindliches Angebot für Ihre nächste Veranstaltung.
    </p>
    <a 
      href="/kontakt" 
      class="inline-block px-8 py-3 bg-white text-[--color-gray-darker] font-semibold rounded hover:bg-gray-100 transition-colors"
    >
      Kontakt aufnehmen
    </a>
  </div>
</section>

<style>
  @keyframes fade-in {
    from {
      opacity: 0;
      transform: translateY(20px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
  
  .animate-fade-in {
    animation: fade-in 1s ease-out;
  }
  
  .animate-fade-in-delay {
    animation: fade-in 1s ease-out 0.3s both;
  }
  
  .animate-fade-in-delay-2 {
    animation: fade-in 1s ease-out 0.6s both;
  }
</style>
