<template>
  <div class="min-h-screen bg-black text-white overflow-x-hidden">
    

    <!-- Navigation -->
    <nav class="fixed top-0 left-0 right-0 z-40 bg-black/90 backdrop-blur-lg border-b border-gray-800">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center h-16">
          <div class="flex items-center">
            <img 
              src="/logo.png" 
              alt="E&S-Luxury Auto Detailing" 
              class="h-10 w-10 sm:h-12 sm:w-12 object-contain"
            />
          </div>
          <div class="hidden md:flex items-center gap-6">
            <a href="#services" class="text-gray-300 hover:text-silver-300 transition-colors">Services</a>
            <a href="#about" class="text-gray-300 hover:text-silver-300 transition-colors">About</a>
            <a href="#testimonials" class="text-gray-300 hover:text-silver-300 transition-colors">Reviews</a>
            <button
              @click="handleCall"
              class="bg-gradient-to-r from-silver-300 to-silver-400 text-black font-bold py-2 px-6 rounded-full hover:shadow-lg hover:shadow-silver-400/30 transition-all duration-300"
            >
              (619) 863-7033
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
    <div v-if="mobileMenuOpen" class="fixed inset-0 z-50 bg-black/95 backdrop-blur-lg md:hidden">
      <div class="flex justify-end p-4">
        <button @click="mobileMenuOpen = false" class="text-white">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
          </svg>
        </button>
      </div>
      <div class="flex flex-col items-center gap-8 mt-12">
        <a href="#services" @click="mobileMenuOpen = false" class="text-2xl text-white hover:text-silver-300 transition-colors">Services</a>
        <a href="#about" @click="mobileMenuOpen = false" class="text-2xl text-white hover:text-silver-300 transition-colors">About</a>
        <a href="#testimonials" @click="mobileMenuOpen = false" class="text-2xl text-white hover:text-silver-300 transition-colors">Reviews</a>
        <button
          @click="handleCall"
          class="text-2xl text-silver-300 font-bold"
        >
          (619) 863-7033
        </button>
      </div>
    </div>

    <!-- Hero Section -->
    <section class="relative min-h-screen flex items-center justify-center overflow-hidden">
      <!-- Hero Background Image -->
      <div class="absolute inset-0 z-0">
        <img 
          src="/hero.png" 
          alt="Luxury Auto Detailing" 
          class="w-full h-full object-cover"
        />
        <div class="absolute inset-0 bg-black/50"></div>
      </div>
      
      <div class="relative z-10 max-w-4xl mx-auto text-center pt-20 px-4 sm:px-6 lg:px-8">
        <div class="mb-6 inline-flex items-center gap-2 bg-silver-400/10 px-4 py-2 rounded-full border border-silver-400/30 backdrop-blur-sm">
          <svg class="w-4 h-4 text-silver-300" fill="currentColor" viewBox="0 0 20 20">
            <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
          </svg>
          <span class="text-sm text-silver-300">San Diego's Premier Mobile Detailing</span>
        </div>
        <h1 class="text-5xl sm:text-6xl lg:text-7xl font-bold mb-6 leading-tight">
          Luxury Auto Detailing
          <span class="block text-3xl sm:text-4xl lg:text-5xl mt-2 bg-gradient-to-r from-silver-300 to-silver-100 bg-clip-text text-transparent">
            Delivered to Your Door
          </span>
        </h1>
        <p class="text-xl sm:text-2xl text-gray-300 mb-8 max-w-2xl mx-auto">
          Experience the pinnacle of automotive care with over 5 years of expertise. Professional detailing, ceramic coating, and paint correction for discerning vehicle owners.
        </p>
        <div class="flex flex-col sm:flex-row gap-4 justify-center">
          <button
            @click="handleBook"
            class="bg-gradient-to-r from-silver-300 to-silver-400 text-black font-bold py-4 px-8 rounded-full text-lg hover:shadow-xl hover:shadow-silver-400/30 transition-all duration-300 transform hover:scale-105"
          >
            Book Your Service
          </button>
          <button
            @click="handleCall"
            class="bg-transparent border-2 border-blue-300 text-blue-300 font-bold py-4 px-8 rounded-full text-lg hover:bg-blue-300 hover:text-black transition-all duration-300 flex items-center justify-center gap-3"
          >
            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
            </svg>
            (619) 863-7033
          </button>
        </div>
      </div>
      <!-- Bottom Gradient -->
      <div class="absolute bottom-0 left-0 right-0 h-32 bg-gradient-to-t from-black to-transparent z-10"></div>
    </section>

    <!-- Trust Indicators -->
    <section class="py-12 px-4 sm:px-6 lg:px-8 border-y border-gray-800 overflow-hidden">
      <div class="max-w-6xl mx-auto">
        <div class="grid grid-cols-2 md:grid-cols-4 gap-4 md:gap-8 text-center">
        <div>
          <div class="text-3xl font-bold text-silver-300">15+</div>
          <div class="text-sm text-gray-400 mt-1">Years Experience</div>
        </div>
        <div>
          <div class="text-3xl font-bold text-silver-300">5,000+</div>
          <div class="text-sm text-gray-400 mt-1">Vehicles Detailed</div>
        </div>
        <div>
          <div class="text-3xl font-bold text-silver-300">5.0★</div>
          <div class="text-sm text-gray-400 mt-1">Google Rating</div>
        </div>
        <div>
          <div class="text-3xl font-bold text-silver-300">100%</div>
          <div class="text-sm text-gray-400 mt-1">Satisfaction</div>
        </div>
        </div>
      </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="py-20 px-4 sm:px-6 lg:px-8">
      <div class="max-w-7xl mx-auto">
        <div class="text-center mb-16">
          <h2 class="text-4xl sm:text-5xl font-bold mb-4">Our Premium Services</h2>
          <p class="text-xl text-gray-400 max-w-2xl mx-auto">
            Comprehensive automotive care solutions tailored to preserve and enhance your vehicle's beauty
          </p>
        </div>
        
        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
          <!-- Service Card 1 -->
          <div class="bg-gradient-to-br from-gray-900 to-gray-800 rounded-2xl border border-gray-700 hover:border-silver-400/50 transition-all duration-300 group overflow-hidden">
            <div class="aspect-w-16 aspect-h-12 overflow-hidden">
              <img 
                src="/fulldetailing.jpg" 
                alt="Full Detail Package" 
                class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-300"
              />
              <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-black/40 to-transparent"></div>
            </div>
            <div class="p-6">
              <h3 class="text-xl font-bold mb-2">Full Detail Package</h3>
              <p class="text-gray-400 text-sm mb-4">Complete interior and exterior transformation with premium products</p>
              <div class="text-2xl font-bold text-silver-300">Starting at $99</div>
            </div>
          </div>

          <!-- Service Card 2 -->
          <div class="bg-gradient-to-br from-gray-900 to-gray-800 rounded-2xl border border-gray-700 hover:border-silver-400/50 transition-all duration-300 group overflow-hidden">
            <div class="aspect-w-16 aspect-h-12 overflow-hidden">
              <img 
                src="/ceramiccoating.png" 
                alt="Ceramic Coating" 
                class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-300"
              />
              <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-black/40 to-transparent"></div>
            </div>
            <div class="p-6">
              <h3 class="text-xl font-bold mb-2">Ceramic Coating</h3>
              <p class="text-gray-400 text-sm mb-4">Ultimate paint protection with hydrophobic nanotechnology</p>
              <div class="text-2xl font-bold text-silver-300">Starting at $500</div>
            </div>
          </div>

          <!-- Service Card 3 -->
          <div class="bg-gradient-to-br from-gray-900 to-gray-800 rounded-2xl border border-gray-700 hover:border-silver-400/50 transition-all duration-300 group overflow-hidden">
            <div class="aspect-w-16 aspect-h-12 overflow-hidden">
              <img 
                src="/paintcorrection2.webp" 
                alt="Paint Correction" 
                class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-300"
              />
              <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-black/40 to-transparent"></div>
            </div>
            <div class="p-6">
              <h3 class="text-xl font-bold mb-2">Paint Correction</h3>
              <p class="text-gray-400 text-sm mb-4">Remove swirls, scratches, and restore factory finish</p>
              <div class="text-2xl font-bold text-silver-300">Starting at $299</div>
            </div>
          </div>

          
        </div>
      </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-20 px-4 sm:px-6 lg:px-8 bg-gradient-to-b from-gray-900 to-black">
      <div class="max-w-7xl mx-auto">
        <div class="grid lg:grid-cols-2 gap-12 items-center">
          <div>
            <h2 class="text-4xl sm:text-5xl font-bold mb-6">
              Setting the Standard for
              <span class="bg-gradient-to-r from-silver-300 to-silver-100 bg-clip-text text-transparent"> Luxury Auto Care</span>
            </h2>
            <p class="text-lg text-gray-300 mb-6">
              With over 15 years of experience in the automotive detailing industry, E&S-Luxury Auto Detailing has established itself as San Diego's premier choice for discerning vehicle owners who demand excellence.
            </p>
            <p class="text-lg text-gray-300 mb-8">
              Our master technicians combine cutting-edge techniques with premium products to deliver results that exceed expectations. From exotic supercars to daily drivers, we treat every vehicle with the meticulous care it deserves.
            </p>
            <div class="space-y-4">
              <div class="flex items-start gap-4">
                <div class="w-6 h-6 rounded-full bg-silver-400/20 flex items-center justify-center flex-shrink-0 mt-0.5">
                  <svg class="w-3 h-3 text-silver-300" fill="currentColor" viewBox="0 0 20 20">
                    <path d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" />
                  </svg>
                </div>
                <div>
                  <h3 class="font-bold mb-1">IDA Certified Professionals</h3>
                  <p class="text-gray-400">International Detailing Association certified technicians</p>
                </div>
              </div>
              <div class="flex items-start gap-4">
                <div class="w-6 h-6 rounded-full bg-silver-400/20 flex items-center justify-center flex-shrink-0 mt-0.5">
                  <svg class="w-3 h-3 text-silver-300" fill="currentColor" viewBox="0 0 20 20">
                    <path d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" />
                  </svg>
                </div>
                <div>
                  <h3 class="font-bold mb-1">Premium Products Only</h3>
                  <p class="text-gray-400">Exclusive use of Gtechniq, Ceramic Pro, and XPEL</p>
                </div>
              </div>
              <div class="flex items-start gap-4">
                <div class="w-6 h-6 rounded-full bg-silver-400/20 flex items-center justify-center flex-shrink-0 mt-0.5">
                  <svg class="w-3 h-3 text-silver-300" fill="currentColor" viewBox="0 0 20 20">
                    <path d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" />
                  </svg>
                </div>
                <div>
                  <h3 class="font-bold mb-1">Mobile Convenience</h3>
                  <p class="text-gray-400">Full-service detailing at your location</p>
                </div>
              </div>
            </div>
          </div>
          <div class="relative">
            <!-- Premium Detail Image -->
            <div class="aspect-square bg-gradient-to-br from-gray-800 to-gray-900 rounded-2xl overflow-hidden shadow-2xl">
              <img 
                src="/detailing.png" 
                alt="Premium Auto Detailing Service" 
                class="w-full h-full object-cover"
              />
              <div class="absolute inset-0 bg-gradient-to-br from-blue-500/10 to-silver-400/10"></div>
            </div>
            <!-- Floating Badge -->
            <div class="absolute -bottom-6 -right-6 bg-gradient-to-r from-silver-300 to-silver-400 text-black p-6 rounded-2xl shadow-2xl">
              <div class="text-3xl font-bold">5+</div>
              <div class="text-sm">Years of Excellence</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Testimonials Section -->
    <section id="testimonials" class="py-20 px-4 sm:px-6 lg:px-8">
      <div class="max-w-7xl mx-auto">
        <div class="text-center mb-16">
          <h2 class="text-4xl sm:text-5xl font-bold mb-4">Client Testimonials</h2>
          <p class="text-xl text-gray-400">Hear from our satisfied luxury vehicle owners</p>
        </div>
        
        <div class="grid md:grid-cols-3 gap-8">
          <!-- Testimonial 1 -->
          <div class="bg-gradient-to-br from-gray-900 to-gray-800 p-8 rounded-2xl border border-gray-700">
            <div class="flex gap-1 mb-4">
              <svg v-for="i in 5" :key="i" class="w-5 h-5 text-silver-300" fill="currentColor" viewBox="0 0 20 20">
                <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
              </svg>
            </div>
            <p class="text-gray-300 mb-6">
              "Exceptional service! They transformed my Porsche 911 to showroom condition. The ceramic coating is flawless, and the convenience of mobile service is unmatched."
            </p>
            <div>
              <div class="font-bold">Michael Chen</div>
              <div class="text-sm text-gray-400">Porsche 911 Turbo Owner</div>
            </div>
          </div>

          <!-- Testimonial 2 -->
          <div class="bg-gradient-to-br from-gray-900 to-gray-800 p-8 rounded-2xl border border-gray-700">
            <div class="flex gap-1 mb-4">
              <svg v-for="i in 5" :key="i" class="w-5 h-5 text-silver-300" fill="currentColor" viewBox="0 0 20 20">
                <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
              </svg>
            </div>
            <p class="text-gray-300 mb-6">
              "E&S has been detailing my vehicles for 5 years. Their attention to detail is incredible, and they treat each car like their own. Highly recommend!"
            </p>
            <div>
              <div class="font-bold">Sarah Williams</div>
              <div class="text-sm text-gray-400">Tesla Model S Owner</div>
            </div>
          </div>

          <!-- Testimonial 3 -->
          <div class="bg-gradient-to-br from-gray-900 to-gray-800 p-8 rounded-2xl border border-gray-700">
            <div class="flex gap-1 mb-4">
              <svg v-for="i in 5" :key="i" class="w-5 h-5 text-silver-300" fill="currentColor" viewBox="0 0 20 20">
                <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
              </svg>
            </div>
            <p class="text-gray-300 mb-6">
              "Professional, punctual, and perfectionist. The paint correction on my BMW M5 exceeded all expectations. Worth every penny!"
            </p>
            <div>
              <div class="font-bold">James Rodriguez</div>
              <div class="text-sm text-gray-400">BMW M5 Owner</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="py-12 px-4 sm:px-6 lg:px-8 border-t border-gray-800">
      <div class="max-w-7xl mx-auto">
        <div class="grid md:grid-cols-4 gap-8 mb-8">
          <div>
            <h3 class="text-xl font-bold mb-4 bg-gradient-to-r from-silver-300 to-silver-100 bg-clip-text text-transparent">
              E&S-Luxury Auto Detailing
            </h3>
            <p class="text-gray-400">
              San Diego's premier mobile detailing service for luxury vehicles.
            </p>
          </div>
          <div>
            <h4 class="font-bold mb-4">Services</h4>
            <ul class="space-y-2 text-gray-400">
              <li><a href="#" class="hover:text-silver-300 transition-colors">Full Detail</a></li>
              <li><a href="#" class="hover:text-silver-300 transition-colors">Ceramic Coating</a></li>
              <li><a href="#" class="hover:text-silver-300 transition-colors">Paint Correction</a></li>
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
              <li class="flex items-center gap-2">
                <svg class="w-4 h-4 text-silver-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
                </svg>
                (619) 863-7033
              </li>
              <li class="flex items-center gap-2">
                <svg class="w-4 h-4 text-silver-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
                Mon-Sun 7AM-8PM
              </li>
            </ul>
          </div>
        </div>
        <div class="pt-8 border-t border-gray-800 text-center text-gray-400">
          <p>&copy; 2025 E&S-Luxury Auto Detailing. All rights reserved.</p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const mobileMenuOpen = ref(false)

const handleCall = () => {
  console.log('Call CTA clicked: (619) 863-7033')
  // In production, this would trigger a phone call
  // window.location.href = 'tel:6198637033'
}

const handleBook = () => {
  console.log('Book appointment CTA clicked')
  // In production, this would open booking system or CRM
}
</script>

<style>
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

/* Additional animations */
@keyframes float {
  0% { transform: translateY(0px); }
  50% { transform: translateY(-10px); }
  100% { transform: translateY(0px); }
}

.animate-float {
  animation: float 3s ease-in-out infinite;
}
</style>