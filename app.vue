<template>
  <div class="min-h-screen bg-black text-white overflow-x-hidden">
    <!-- Navigation -->
    <nav class="fixed top-0 left-0 right-0 z-40 bg-black/90 backdrop-blur-lg border-b border-gray-800">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center h-16">
          <div class="flex items-center">
            <span class="text-xl font-bold bg-gradient-to-r from-white to-blue-300 bg-clip-text text-transparent">
              E&S Luxury
            </span>
          </div>
          <div class="hidden md:flex items-center gap-6">
            <a href="#services" class="text-gray-300 hover:text-blue-300 transition-colors">Services</a>
            <a href="#gallery" class="text-gray-300 hover:text-blue-300 transition-colors">Gallery</a>
            <a href="#about" class="text-gray-300 hover:text-blue-300 transition-colors">About</a>
            <a href="#testimonials" class="text-gray-300 hover:text-blue-300 transition-colors">Reviews</a>
            <button
              @click="handleCall"
              class="bg-blue-300 text-black font-medium py-2 px-6 rounded-full hover:bg-blue-400 transition-all duration-300"
            >
              Call Now
            </button>
          </div>
          <button @click="mobileMenuOpen = !mobileMenuOpen" class="md:hidden text-white">
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
            </svg>
          </button>
        </div>
      </div>
    </nav>

    <!-- Mobile Menu -->
    <div v-if="mobileMenuOpen" class="fixed inset-0 z-50 bg-black/98 backdrop-blur-lg md:hidden">
      <div class="flex justify-end p-4">
        <button @click="mobileMenuOpen = false" class="text-white">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
          </svg>
        </button>
      </div>
      <div class="flex flex-col items-center justify-center h-full space-y-8 -mt-20">
        <a href="#services" @click="mobileMenuOpen = false" class="text-2xl hover:text-gray-300 transition-colors">Services</a>
        <a href="#gallery" @click="mobileMenuOpen = false" class="text-2xl hover:text-gray-300 transition-colors">Gallery</a>
        <a href="#about" @click="mobileMenuOpen = false" class="text-2xl hover:text-gray-300 transition-colors">About</a>
        <a href="#testimonials" @click="mobileMenuOpen = false" class="text-2xl hover:text-gray-300 transition-colors">Reviews</a>
        <button
          @click="handleCall"
          class="text-2xl text-white font-bold"
        >
          (619) 863-7033
        </button>
      </div>
    </div>

    <!-- Hero Section with Video Background -->
    <section class="relative h-screen flex items-center justify-center overflow-hidden">
      <!-- Video Background -->
      <div class="absolute inset-0">
        <video 
          autoplay 
          muted 
          loop 
          playsinline
          class="absolute inset-0 w-full h-full object-cover"
        >
          <source src="/washing.mp4" type="video/mp4">
        </video>
        <div class="absolute inset-0 bg-gradient-to-b from-black/40 via-black/50 to-black/70"></div>
      </div>
      
      <!-- Hero Content -->
      <div class="relative z-10 text-center px-4 max-w-4xl mx-auto">
        <h1 class="text-5xl md:text-7xl font-bold mb-6 animate-fade-in">
          Luxury Auto <span class="text-blue-300">Detailing</span>
          <span class="block text-3xl md:text-4xl mt-4 font-light text-gray-300">
            Delivered to Your Door
          </span>
        </h1>
        <p class="text-xl md:text-2xl text-gray-300 mb-8 max-w-2xl mx-auto animate-fade-in-delay">
          Professional detailing service with over 15 years of expertise
        </p>
        <div class="flex flex-col sm:flex-row gap-4 justify-center animate-fade-in-delay-2">
          <button
            @click="handleBook"
            class="bg-blue-300 text-black px-8 py-4 rounded-full font-bold text-lg hover:bg-blue-400 transform hover:scale-105 transition-all duration-200"
          >
            Book Your Service
          </button>
          <button
            @click="handleCall"
            class="border-2 border-blue-300 text-blue-300 px-8 py-4 rounded-full font-bold text-lg hover:bg-blue-300 hover:text-black transition-all duration-200"
          >
            (619) 863-7033
          </button>
        </div>
      </div>
      
      <!-- Scroll Indicator -->
      <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce">
        <svg class="w-6 h-6 text-white/50" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3" />
        </svg>
      </div>
    </section>

    <!-- Trust Indicators -->
    <section class="py-16 px-4 bg-gradient-to-b from-black to-gray-950">
      <div class="max-w-6xl mx-auto">
        <div class="grid grid-cols-2 md:grid-cols-4 gap-8 text-center">
          <div class="animate-fade-in">
            <div class="text-4xl font-bold mb-2">15+</div>
            <div class="text-gray-400">Years Experience</div>
          </div>
          <div class="animate-fade-in-delay">
            <div class="text-4xl font-bold mb-2">5,000+</div>
            <div class="text-gray-400">Vehicles Detailed</div>
          </div>
          <div class="animate-fade-in-delay-2">
            <div class="text-4xl font-bold mb-2">5.0<span class="text-blue-300">★</span></div>
            <div class="text-gray-400">Google Rating</div>
          </div>
          <div class="animate-fade-in-delay-3">
            <div class="text-4xl font-bold mb-2">100%</div>
            <div class="text-gray-400">Satisfaction</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Gallery Section -->
    <section id="gallery" class="py-20 px-4 bg-gray-950">
      <div class="max-w-7xl mx-auto">
        <div class="text-center mb-16">
          <h2 class="text-4xl md:text-5xl font-bold mb-4">Our <span class="text-blue-300">Work</span></h2>
          <p class="text-xl text-gray-400">See the difference professional detailing makes</p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
          <!-- Image Gallery Items -->
          <div class="relative group overflow-hidden rounded-2xl">
            <img 
              src="/still.jpeg" 
              alt="Detail Work 1" 
              class="w-full h-[500px] md:h-[400px] object-cover transform group-hover:scale-105 transition-transform duration-500"
            >
            <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
          </div>
          
          <div class="relative group overflow-hidden rounded-2xl">
            <img 
              src="/still2.jpeg" 
              alt="Detail Work 2" 
              class="w-full h-[500px] md:h-[400px] object-cover transform group-hover:scale-105 transition-transform duration-500"
            >
            <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
          </div>
          
          <div class="relative group overflow-hidden rounded-2xl">
            <img 
              src="/still3.jpeg" 
              alt="Detail Work 3" 
              class="w-full h-[500px] md:h-[400px] object-cover transform group-hover:scale-105 transition-transform duration-500"
            >
            <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
          </div>
          
          <!-- Video Gallery Items -->
          <div class="relative group overflow-hidden rounded-2xl md:col-span-2 lg:col-span-1">
            <video 
              autoplay 
              muted 
              loop 
              playsinline
              class="w-full h-[500px] md:h-[400px] object-cover"
            >
              <source src="/washing2.mp4" type="video/mp4">
            </video>
            <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent pointer-events-none"></div>
            <div class="absolute bottom-4 left-4 text-white">
              <p class="text-sm font-medium">Professional Washing</p>
            </div>
          </div>
          
          <div class="relative group overflow-hidden rounded-2xl md:col-span-2 lg:col-span-2">
            <video 
              autoplay 
              muted 
              loop 
              playsinline
              class="w-full h-[500px] md:h-[400px] object-cover"
            >
              <source src="/washing3.mp4" type="video/mp4">
            </video>
            <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent pointer-events-none"></div>
            <div class="absolute bottom-4 left-4 text-white">
              <p class="text-sm font-medium">Precision Detailing</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="py-20 px-4 bg-black">
      <div class="max-w-7xl mx-auto">
        <div class="text-center mb-16">
          <h2 class="text-4xl md:text-5xl font-bold mb-4">Our <span class="text-blue-300">Services</span></h2>
          <p class="text-xl text-gray-400">Professional care for your vehicle</p>
        </div>
        
        <div class="grid md:grid-cols-3 gap-8">
          <!-- Service Cards -->
          <div class="bg-gray-900/50 backdrop-blur-sm border border-gray-800 rounded-2xl p-8 hover:border-gray-600 transition-all duration-300">
            <div class="w-16 h-16 bg-white/10 rounded-full flex items-center justify-center mb-6">
              <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
              </svg>
            </div>
            <h3 class="text-2xl font-bold mb-4">Full Detail</h3>
            <p class="text-gray-400 mb-6">Complete interior and exterior transformation with premium products and meticulous attention to detail.</p>
            <div class="text-3xl font-bold text-blue-300">$99+</div>
          </div>
          
          <div class="bg-gray-900/50 backdrop-blur-sm border border-gray-800 rounded-2xl p-8 hover:border-gray-600 transition-all duration-300">
            <div class="w-16 h-16 bg-white/10 rounded-full flex items-center justify-center mb-6">
              <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z" />
              </svg>
            </div>
            <h3 class="text-2xl font-bold mb-4">Ceramic Coating</h3>
            <p class="text-gray-400 mb-6">Ultimate paint protection with hydrophobic nanotechnology for lasting shine and protection.</p>
            <div class="text-3xl font-bold text-blue-300">$500+</div>
          </div>
          
          <div class="bg-gray-900/50 backdrop-blur-sm border border-gray-800 rounded-2xl p-8 hover:border-gray-600 transition-all duration-300">
            <div class="w-16 h-16 bg-white/10 rounded-full flex items-center justify-center mb-6">
              <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 3v4M3 5h4M6 17v4m-2-2h4m5-16l2.286 6.857L21 12l-5.714 2.143L13 21l-2.286-6.857L5 12l5.714-2.143L13 3z" />
              </svg>
            </div>
            <h3 class="text-2xl font-bold mb-4">Paint Correction</h3>
            <p class="text-gray-400 mb-6">Remove swirls, scratches, and imperfections to restore your vehicle's factory finish.</p>
            <div class="text-3xl font-bold text-blue-300">$299+</div>
          </div>
        </div>
      </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-20 px-4 bg-gray-950">
      <div class="max-w-7xl mx-auto">
        <div class="grid lg:grid-cols-2 gap-12 items-center">
          <div>
            <h2 class="text-4xl md:text-5xl font-bold mb-6">
              Why Choose <span class="text-blue-300">E&S Luxury?</span>
            </h2>
            <p class="text-lg text-gray-300 mb-8">
              With over 15 years of experience, we've perfected the art of automotive detailing. Our commitment to excellence and attention to detail sets us apart.
            </p>
            
            <div class="space-y-6">
              <div class="flex items-start gap-4">
                <div class="w-12 h-12 bg-white/10 rounded-full flex items-center justify-center flex-shrink-0">
                  <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                  </svg>
                </div>
                <div>
                  <h3 class="text-xl font-bold mb-2">Mobile Service</h3>
                  <p class="text-gray-400">We come to you - home, office, or anywhere convenient</p>
                </div>
              </div>
              
              <div class="flex items-start gap-4">
                <div class="w-12 h-12 bg-white/10 rounded-full flex items-center justify-center flex-shrink-0">
                  <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                  </svg>
                </div>
                <div>
                  <h3 class="text-xl font-bold mb-2">Premium Products</h3>
                  <p class="text-gray-400">Only the finest detailing products and equipment</p>
                </div>
              </div>
              
              <div class="flex items-start gap-4">
                <div class="w-12 h-12 bg-white/10 rounded-full flex items-center justify-center flex-shrink-0">
                  <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                  </svg>
                </div>
                <div>
                  <h3 class="text-xl font-bold mb-2">Satisfaction Guaranteed</h3>
                  <p class="text-gray-400">Your complete satisfaction is our top priority</p>
                </div>
              </div>
            </div>
          </div>
          
          <div class="relative">
            <div class="aspect-square rounded-2xl overflow-hidden">
              <video 
                autoplay 
                muted 
                loop 
                playsinline
                class="w-full h-full object-cover"
              >
                <source src="/washing.mp4" type="video/mp4">
              </video>
              <div class="absolute inset-0 bg-gradient-to-t from-black/40 to-transparent"></div>
            </div>
            <div class="absolute -bottom-6 -right-6 bg-blue-300 text-black p-6 rounded-2xl shadow-2xl">
              <div class="text-3xl font-bold">5★</div>
              <div class="text-sm">Google Rating</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Testimonials -->
    <section id="testimonials" class="py-20 px-4 bg-black">
      <div class="max-w-7xl mx-auto">
        <div class="text-center mb-16">
          <h2 class="text-4xl md:text-5xl font-bold mb-4">What Our <span class="text-blue-300">Clients Say</span></h2>
          <p class="text-xl text-gray-400">Real reviews from satisfied customers</p>
        </div>
        
        <div class="grid md:grid-cols-3 gap-8">
          <div class="bg-gray-900/50 backdrop-blur-sm border border-gray-800 rounded-2xl p-8">
            <div class="flex gap-1 mb-4">
              <svg v-for="i in 5" :key="i" class="w-5 h-5 text-yellow-500" fill="currentColor" viewBox="0 0 20 20">
                <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
              </svg>
            </div>
            <p class="text-gray-300 mb-6">
              "Exceptional service! They transformed my car to showroom condition. The attention to detail is outstanding."
            </p>
            <div>
              <div class="font-bold">Michael Chen</div>
              <div class="text-sm text-gray-400">Porsche Owner</div>
            </div>
          </div>
          
          <div class="bg-gray-900/50 backdrop-blur-sm border border-gray-800 rounded-2xl p-8">
            <div class="flex gap-1 mb-4">
              <svg v-for="i in 5" :key="i" class="w-5 h-5 text-yellow-500" fill="currentColor" viewBox="0 0 20 20">
                <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
              </svg>
            </div>
            <p class="text-gray-300 mb-6">
              "Professional and reliable. The convenience of mobile service is amazing. My Tesla looks brand new!"
            </p>
            <div>
              <div class="font-bold">Sarah Williams</div>
              <div class="text-sm text-gray-400">Tesla Owner</div>
            </div>
          </div>
          
          <div class="bg-gray-900/50 backdrop-blur-sm border border-gray-800 rounded-2xl p-8">
            <div class="flex gap-1 mb-4">
              <svg v-for="i in 5" :key="i" class="w-5 h-5 text-yellow-500" fill="currentColor" viewBox="0 0 20 20">
                <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
              </svg>
            </div>
            <p class="text-gray-300 mb-6">
              "Best detailing service in San Diego! The paint correction made my BMW look better than new."
            </p>
            <div>
              <div class="font-bold">James Rodriguez</div>
              <div class="text-sm text-gray-400">BMW Owner</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="py-20 px-4 bg-gradient-to-r from-gray-900 to-black">
      <div class="max-w-4xl mx-auto text-center">
        <h2 class="text-4xl md:text-5xl font-bold mb-6">Ready to Experience <span class="text-blue-300">Luxury?</span></h2>
        <p class="text-xl text-gray-300 mb-8">Book your professional detailing service today</p>
        <div class="flex flex-col sm:flex-row gap-4 justify-center">
          <button
            @click="handleBook"
            class="bg-blue-300 text-black px-8 py-4 rounded-full font-bold text-lg hover:bg-blue-400 transform hover:scale-105 transition-all duration-200"
          >
            Book Now
          </button>
          <button
            @click="handleCall"
            class="border-2 border-blue-300 text-blue-300 px-8 py-4 rounded-full font-bold text-lg hover:bg-blue-300 hover:text-black transition-all duration-200"
          >
            Call (619) 863-7033
          </button>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="py-12 px-4 border-t border-gray-800">
      <div class="max-w-7xl mx-auto">
        <div class="grid md:grid-cols-4 gap-8 mb-8">
          <div>
            <h3 class="text-xl font-bold mb-4 text-blue-300">E&S Luxury Auto Detailing</h3>
            <p class="text-gray-400">San Diego's premier mobile detailing service.</p>
          </div>
          <div>
            <h4 class="font-bold mb-4">Services</h4>
            <ul class="space-y-2 text-gray-400">
              <li>Full Detail</li>
              <li>Ceramic Coating</li>
              <li>Paint Correction</li>
            </ul>
          </div>
          <div>
            <h4 class="font-bold mb-4">Service Areas</h4>
            <ul class="space-y-2 text-gray-400">
              <li>La Jolla</li>
              <li>Del Mar</li>
              <li>Carlsbad</li>
              <li>All San Diego County</li>
            </ul>
          </div>
          <div>
            <h4 class="font-bold mb-4">Contact</h4>
            <ul class="space-y-2 text-gray-400">
              <li>(619) 863-7033</li>
              <li>Mon-Sun 7AM-8PM</li>
            </ul>
          </div>
        </div>
        <div class="pt-8 border-t border-gray-800 text-center text-gray-400">
          <p>&copy; 2025 E&S Luxury Auto Detailing. All rights reserved.</p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const mobileMenuOpen = ref(false)

const handleCall = () => {
  window.location.href = 'tel:6198637033'
}

const handleBook = () => {
  console.log('Book appointment CTA clicked')
  // In production, this would open booking system or CRM
}

// Add intersection observer for animations
onMounted(() => {
  const observerOptions = {
    threshold: 0.1,
    rootMargin: '0px 0px -50px 0px'
  }
  
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('opacity-100', 'translate-y-0')
        entry.target.classList.remove('opacity-0', 'translate-y-4')
      }
    })
  }, observerOptions)
  
  // Observe all sections
  document.querySelectorAll('section').forEach(section => {
    section.classList.add('opacity-0', 'translate-y-4', 'transition-all', 'duration-700')
    observer.observe(section)
  })
})
</script>

<style scoped>
/* Custom scrollbar styling for luxury feel */
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-track {
  background: #111;
}

::-webkit-scrollbar-thumb {
  background: #444;
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: #666;
}

/* Smooth scroll behavior */
html {
  scroll-behavior: smooth;
}

/* Animation classes */
@keyframes fadeIn {
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
  animation: fadeIn 0.8s ease-out forwards;
}

.animate-fade-in-delay {
  animation: fadeIn 0.8s ease-out 0.2s forwards;
  opacity: 0;
}

.animate-fade-in-delay-2 {
  animation: fadeIn 0.8s ease-out 0.4s forwards;
  opacity: 0;
}

.animate-fade-in-delay-3 {
  animation: fadeIn 0.8s ease-out 0.6s forwards;
  opacity: 0;
}
</style>