<script>
  let formData = {
    name: '',
    email: '',
    phone: '',
    message: ''
  };
  
  let isSubmitting = false;
  let submitMessage = '';
  
  async function handleSubmit(e) {
    e.preventDefault();
    isSubmitting = true;
    
    // Hier würde normalerweise der Form-Submit an einen Server erfolgen
    // Für diese Demo zeigen wir nur eine Erfolgsmeldung
    setTimeout(() => {
      submitMessage = 'Vielen Dank für Ihre Nachricht! Wir melden uns schnellstmöglich bei Ihnen.';
      isSubmitting = false;
      formData = {
        name: '',
        email: '',
        phone: '',
        message: ''
      };
    }, 1000);
  }
</script>

<svelte:head>
  <title>Kontakt - Division System</title>
  <meta name="description" content="Kontaktieren Sie Division System für professionelle Lautsprecher-Vermietung in Bielefeld." />
</svelte:head>

<section class="py-20">
  <div class="container-custom">
    <div class="max-w-4xl mx-auto">
      <h1 class="text-4xl md:text-5xl font-bold text-white mb-8 text-center">
        Kontakt
      </h1>
      
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-12">
        <!-- Contact Form -->
        <div class="bg-[--color-gray-ral7016] p-8 rounded-lg">
          <h2 class="text-2xl font-semibold text-white mb-6">
            Nachricht senden
          </h2>
          
          <form on:submit={handleSubmit} class="space-y-6">
            <div>
              <label for="name" class="block text-gray-300 mb-2">Name *</label>
              <input
                type="text"
                id="name"
                bind:value={formData.name}
                required
                class="w-full px-4 py-3 bg-[--color-gray-dark] border border-gray-600 rounded text-white focus:outline-none focus:border-white transition-colors"
              />
            </div>
            
            <div>
              <label for="email" class="block text-gray-300 mb-2">E-Mail *</label>
              <input
                type="email"
                id="email"
                bind:value={formData.email}
                required
                class="w-full px-4 py-3 bg-[--color-gray-dark] border border-gray-600 rounded text-white focus:outline-none focus:border-white transition-colors"
              />
            </div>
            
            <div>
              <label for="phone" class="block text-gray-300 mb-2">Telefon</label>
              <input
                type="tel"
                id="phone"
                bind:value={formData.phone}
                class="w-full px-4 py-3 bg-[--color-gray-dark] border border-gray-600 rounded text-white focus:outline-none focus:border-white transition-colors"
              />
            </div>
            
            <div>
              <label for="message" class="block text-gray-300 mb-2">Nachricht *</label>
              <textarea
                id="message"
                bind:value={formData.message}
                required
                rows="6"
                class="w-full px-4 py-3 bg-[--color-gray-dark] border border-gray-600 rounded text-white focus:outline-none focus:border-white transition-colors resize-none"
              ></textarea>
            </div>
            
            <button
              type="submit"
              disabled={isSubmitting}
              class="w-full px-6 py-3 bg-white text-black font-semibold rounded hover:bg-gray-100 transition-colors disabled:opacity-50 disabled:cursor-not-allowed"
            >
              {isSubmitting ? 'Wird gesendet...' : 'Nachricht senden'}
            </button>
            
            {#if submitMessage}
              <p class="text-green-400 text-center">{submitMessage}</p>
            {/if}
          </form>
        </div>
        
        <!-- Contact Info -->
        <div class="space-y-8">
          <div class="bg-[--color-gray-ral7016] p-8 rounded-lg">
            <h2 class="text-2xl font-semibold text-white mb-6">
              Kontaktinformationen
            </h2>
            
            <div class="space-y-6">
              <div>
                <h3 class="text-white font-semibold mb-2">Adresse</h3>
                <address class="text-gray-300 not-italic">
                  Division System<br>
                  August-Bebel-Straße 84<br>
                  33602 Bielefeld<br>
                  Deutschland
                </address>
              </div>
              
              <div>
                <h3 class="text-white font-semibold mb-2">Öffnungszeiten</h3>
                <p class="text-gray-300">
                  Montag - Freitag: 9:00 - 18:00 Uhr<br>
                  Samstag: Nach Vereinbarung<br>
                  Sonntag: Geschlossen
                </p>
              </div>
            </div>
          </div>
          
          <!-- Map Placeholder -->
          <div class="bg-[--color-gray-ral7016] p-8 rounded-lg">
            <h3 class="text-white font-semibold mb-4">Standort</h3>
            <div class="aspect-video bg-[--color-gray-dark] rounded flex items-center justify-center">
              <p class="text-gray-500">Karte wird hier angezeigt</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
