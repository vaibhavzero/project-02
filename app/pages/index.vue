<template>
  <div class="min-h-screen bg-white">

    <!-- Modern Navigation -->
    <nav class="fixed top-0 left-0 right-0 bg-white/95 backdrop-blur-lg border-b border-gray-100 z-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center h-14 md:h-20">
          <div class="flex items-center gap-2">
            <img src="../assets/imgs/logo.png" alt="" class="w-10 h-10 md:w-14 md:h-14">
            <span class="text-xl md:text-2xl font-bold text-gray-900">BMAI</span>
          </div>
          <div class="hidden md:flex items-center gap-8">
            <button @click="scrollTo('services')"
              class="text-gray-600 hover:text-emerald-600 transition-colors font-medium">Services</button>
            <button @click="scrollTo('process')"
              class="text-gray-600 hover:text-emerald-600 transition-colors font-medium">Process</button>
            <button @click="scrollTo('trust')"
              class="text-gray-600 hover:text-emerald-600 transition-colors font-medium">About</button>
            <button @click="scrollTo('contact')"
              class="text-gray-600 hover:text-emerald-600 transition-colors font-medium">Contact</button>
            <button @click="scrollTo('contact')"
              class="bg-emerald-600 hover:bg-emerald-700 text-white px-6 py-2.5 rounded-full font-medium transition-all duration-200 hover:scale-105">
              Get Started
            </button>
          </div>
          <!-- Mobile hamburger -->
          <div class="md:hidden">
            <UButton icon="i-lucide-menu" variant="ghost" color="gray" aria-label="Open menu"
              @click="mobileOpen = true" />
          </div>
        </div>
      </div>
    </nav>

    <!-- Mobile Menu -->
    <USlideover v-model:open="mobileOpen" side="right" class="md:hidden" :ui="{
      content: 'bg-white'
    }">
      <template #content>
        <div class="p-4 space-y-4 bg-white">
          <div class="flex items-center justify-between mb-2">
            <span class="text-lg font-semibold px-2">Menu</span>
            <UButton icon="i-lucide-x" variant="ghost" color="gray" aria-label="Close menu"
              @click="mobileOpen = false" />
          </div>
          <div class="flex flex-col space-y-2">
            <UButton variant="ghost" color="gray" @click="scrollTo('services'); mobileOpen = false">Services</UButton>
            <UButton variant="ghost" color="gray" @click="scrollTo('process'); mobileOpen = false">Process</UButton>
            <UButton variant="ghost" color="gray" @click="scrollTo('trust'); mobileOpen = false">About</UButton>
            <UButton variant="ghost" color="gray" @click="scrollTo('contact'); mobileOpen = false">Contact</UButton>
            <UButton color="success" class="mt-2" @click="scrollTo('contact'); mobileOpen = false">Get Started</UButton>
          </div>
        </div>
      </template>
    </USlideover>

    <!-- Modern Hero Section -->
    <section class="min-h-[calc(100dvh-80px)] pt-20 px-4 flex items-center py-4 sm:py-4 md:py-4">
      <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid lg:grid-cols-2  md:gap-10 lg:gap-12 items-center">
          <!-- Image on top for mobile/md -->
          <div class="lg:hidden relative mb-6 md:mb-8 mt-4 md:mt-0">
            <img
              src="https://media.istockphoto.com/id/1334594420/photo/makhana-is-lotus-seeds-or-fox-nuts-used-to-preparing-various-foods-in-india.jpg?s=612x612&w=0&k=20&c=jaUb_emwnyOJWh506PO4Vy6y88tcZQObG0zyCvBypSQ="
              alt="Makhana bowl" class="w-full h-48 md:h-56 object-cover rounded-2xl" />
            <div
              class="absolute bottom-3 left-1/2 -translate-x-1/2 bg-white/90 backdrop-blur-sm px-4 py-2 md:px-5 md:py-2.5 rounded-full border border-emerald-100 flex items-center gap-2 md:gap-2.5">
              <UIcon name="i-heroicons-sparkles" class="text-emerald-600 text-base md:text-lg" />
              <span class="text-xs md:text-sm font-semibold text-gray-900">Export-ready from day one</span>
            </div>
          </div>

          <div class="space-y-4 md:space-y-5">
            <h1 class="text-3xl md:text-4xl lg:text-5xl font-semibold text-gray-900 leading-tight">
              Your Makhana Partner from <span class="text-emerald-600">Bihar to Shelf</span>
            </h1>
            <p class="text-base md:text-lg text-gray-600">
              Quality, size, variety—exactly what your market needs, delivered with zero guesswork.
            </p>

            <div class="flex gap-2 md:gap-3">
              <UButton @click="scrollTo('contact')" color="success" variant="solid"
                icon="i-heroicons-clipboard-document" class="text-sm md:text-base">
                Request Sample
              </UButton>
              <UButton @click="scrollTo('samples')" color="success" variant="ghost" icon="i-heroicons-phone"
                class="text-sm md:text-base">
                Book Call
              </UButton>
            </div>
          </div>

          <!-- Image on right for lg+ -->
          <div class="hidden lg:block relative">
            <img
              src="https://media.istockphoto.com/id/1334594420/photo/makhana-is-lotus-seeds-or-fox-nuts-used-to-preparing-various-foods-in-india.jpg?s=612x612&w=0&k=20&c=jaUb_emwnyOJWh506PO4Vy6y88tcZQObG0zyCvBypSQ="
              alt="Makhana bowl" class="w-full h-64 object-cover rounded-2xl" />
            <div
              class="absolute bottom-4 left-1/2 -translate-x-1/2 bg-white/90 backdrop-blur-sm px-4 py-2 rounded-full border border-emerald-100 flex items-center gap-2">
              <UIcon name="i-heroicons-sparkles" class="text-emerald-600 text-lg" />
              <span class="text-sm font-semibold text-gray-900">Export-ready from day one</span>
            </div>
          </div>
        </div>
      </div>
    </section>




    <!-- Who We Serve Section -->
    <section class="py-8 pb-24 bg-gradient-to-b from-gray-50 to-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <!-- Header -->
        <div class="text-center mb-10">
          <UBadge color="info" variant="subtle" size="md" class="mb-3 md:mb-4" icon="i-heroicons-tag">
            Tailored Solutions
          </UBadge>

          <h2 class="text-2xl sm:text-3xl md:text-4xl lg:text-5xl font-bold text-gray-900 mb-4 md:mb-6">
            Serving Every Segment of the
            <span class="block mt-1 md:mt-2 text-gray-700">Makhana Market</span>
          </h2>

          <p class="text-sm sm:text-base md:text-lg text-gray-600 max-w-2xl mx-auto">
            From bulk wholesalers to private label brands, we deliver tailored solutions for your business needs
          </p>
        </div>

        <!-- Services Grid -->
        <div class="grid lg:grid-cols-3 gap-8">
          <!-- Wholesaler -->
          <div class="group shadow-2xl p-8 rounded-2xl transition-all duration-300 border border-neutral-300">
            <div class="space-y-6">
              <!-- Icon -->
              <div
                class="inline-flex p-4 bg-success-500 rounded-xl group-hover:scale-110 transition-transform duration-300">
                <UIcon name="i-heroicons-building-storefront" class="text-white text-3xl" />
              </div>

              <!-- Title & Stats -->
              <div>
                <h3 class="text-2xl font-bold text-gray-900 mb-2">Wholesalers</h3>
                <UBadge color="success" variant="subtle" icon="i-heroicons-check-circle-solid">500+ Tons Monthly
                </UBadge>

              </div>
              <!-- Features -->
              <ul class="space-y-3">
                <li class="flex items-start gap-3">
                  <UIcon name="i-heroicons-bolt" class="text-gray-900 flex-shrink-0 mt-0.5 text-xl" />
                  <span class="text-sm text-gray-600">Reliable bulk supply with consistent quality</span>
                </li>
                <li class="flex items-start gap-3">
                  <UIcon name="i-heroicons-tag" class="text-gray-900 flex-shrink-0 mt-0.5 text-xl" />
                  <span class="text-sm text-gray-600">Transparent pricing and volume discounts</span>
                </li>
                <li class="flex items-start gap-3">
                  <UIcon name="i-heroicons-calendar" class="text-gray-900 flex-shrink-0 mt-0.5 text-xl" />
                  <span class="text-sm text-gray-600">Flexible delivery schedules</span>
                </li>
              </ul>

              <!-- CTA -->
              <UButton block size="lg" variant="ghost" trailing-icon="i-heroicons-arrow-right"
                @click="scrollTo('contact')" class="font-semibold text-black">
                Get Bulk Quote
              </UButton>
            </div>
          </div>

          <!-- Retailer -->
          <div
            class="group shadow-2xl p-8 rounded-2xl transition-all duration-300 border border-gray-100 border-neutral-300">
            <div class="space-y-6">
              <!-- Icon -->
              <div
                class="inline-flex p-4 bg-info-500 rounded-xl group-hover:scale-110 transition-transform duration-300">
                <UIcon name="i-heroicons-shopping-cart" class="text-white text-3xl" />
              </div>

              <!-- Title & Stats -->
              <div>
                <h3 class="text-2xl font-bold text-gray-900 mb-2">Retailers</h3>
                <UBadge color="success" variant="subtle" icon="i-heroicons-check-circle-solid">50KG Min order</UBadge>

              </div>
              <!-- Features -->
              <ul class="space-y-3">
                <li class="flex items-start gap-3">
                  <UIcon name="i-heroicons-bolt" class="text-gray-900 flex-shrink-0 mt-0.5 text-xl" />
                  <span class="text-sm text-gray-600">Pre-packed branded/semi-branded options</span>
                </li>
                <li class="flex items-start gap-3">
                  <UIcon name="i-heroicons-tag" class="text-gray-900 flex-shrink-0 mt-0.5 text-xl" />
                  <span class="text-sm text-gray-600">Small MOQ for testing market response</span>
                </li>
                <li class="flex items-start gap-3">
                  <UIcon name="i-heroicons-calendar" class="text-gray-900 flex-shrink-0 mt-0.5 text-xl" />
                  <span class="text-sm text-gray-600">Fast delivery to your stores</span>
                </li>
              </ul>

              <!-- CTA -->
              <UButton block size="lg" variant="ghost" trailing-icon="i-heroicons-arrow-right"
                @click="scrollTo('contact')" class="font-semibold text-black">
                Explore Retail Options
              </UButton>
            </div>
          </div>



          <!-- Private Label -->

          <div class="group shadow-2xl p-8 rounded-2xl transition-all duration-300 border border-neutral-300">
            <div class="space-y-6">
              <!-- Icon -->
              <div
                class="inline-flex p-4 bg-warning-500 rounded-xl group-hover:scale-110 transition-transform duration-300">
                <UIcon name="i-heroicons-tag" class="text-white text-3xl" />
              </div>

              <!-- Title & Stats -->
              <div>
                <h3 class="text-2xl font-bold text-gray-900 mb-2">Private Label</h3>
                <UBadge color="success" variant="subtle" icon="i-heroicons-check-circle-solid">₹0 Upfront Cost</UBadge>

              </div>
              <!-- Features -->
              <ul class="space-y-3">
                <li class="flex items-start gap-3">
                  <UIcon name="i-heroicons-bolt" class="text-gray-900 flex-shrink-0 mt-0.5 text-xl" />
                  <span class="text-sm text-gray-600">Zero investment learning approach
                  </span>
                </li>
                <li class="flex items-start gap-3">
                  <UIcon name="i-heroicons-tag" class="text-gray-900 flex-shrink-0 mt-0.5 text-xl" />
                  <span class="text-sm text-gray-600">Refundable samples for testing
                  </span>
                </li>
                <li class="flex items-start gap-3">
                  <UIcon name="i-heroicons-calendar" class="text-gray-900 flex-shrink-0 mt-0.5 text-xl" />
                  <span class="text-sm text-gray-600">End-to-end brand support
                  </span>
                </li>
              </ul>

              <!-- CTA -->
              <UButton block size="lg" variant="ghost" trailing-icon="i-heroicons-arrow-right"
                @click="scrollTo('contact')" class="font-semibold text-black">
                Start Your Brand
              </UButton>
            </div>
          </div>


        </div>

        <!-- Bottom CTA -->
        <div class="mt-16 text-center">
          <p class="text-gray-600 mb-4">Not sure which solution fits your needs?</p>
          <UButton size="lg" color="success" variant="solid" trailing-icon="i-heroicons-arrow-right"
            @click="scrollTo('contact')">
            Talk to Our Expert
          </UButton>
        </div>
      </div>
    </section>

    <!-- The Journey Section -->
    <section id="process" class="py-24 bg-emerald-50 relative overflow-hidden">
      <!-- Decorative blobs -->
      <div class="absolute -top-20 -left-20 w-64 h-64 bg-emerald-200 rounded-full blur-3xl opacity-30"></div>
      <div class="absolute -bottom-20 -right-20 w-80 h-80 bg-amber-200 rounded-full blur-3xl opacity-30"></div>
      <div
        class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-96 h-96 bg-white/20 rounded-full blur-3xl">
      </div>

      <!-- Floating shapes -->


      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
        <div class="text-center mb-16 flex-col">
          <div class="inline-flex items-center gap-3 mb-4">
            <h2 class="text-3xl lg:text-4xl font-bold text-gray-900">
              Your Brand Building Ecosystem
            </h2>
          </div>
          <div>
            <UBadge color="success" variant="subtle" size="lg" class="mb-4" icon="i-heroicons-light-bulb">
              Four steps to launch your brand
            </UBadge>
          </div>
        </div>

        <div class="mx-auto">
          <UStepper v-model="active" :items="items" class="w-full" size="md" :ui="{
            title: 'text-black',
          }" :orientation="isMdAndSm ? 'vertical' : 'horizontal'">
          </UStepper>
        </div>
      </div>
    </section>

    <!-- Why Choose BMAI Section -->
    <section class="py-12 md:py-16 lg:py-24 bg-gray-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <!-- Header -->
        <div class="text-center mb-8 md:mb-12 lg:mb-16">
          <h2 class="text-2xl md:text-4xl lg:text-5xl font-bold text-gray-900 mb-2 md:mb-4">
            Why Choose BMAI
          </h2>
          <p class="text-sm md:text-lg text-gray-600 max-w-2xl mx-auto px-4">
            Trusted expertise from Bihar's makhana heartland to your business success
          </p>
        </div>

        <!-- Features - Mobile: Vertical List, Desktop: Zigzag Timeline -->
        <div class="relative">
          <!-- Central line - Hidden on mobile, visible on lg+ -->
          <div
            class="hidden lg:block absolute left-1/2 top-0 bottom-0 w-1 bg-gradient-to-b from-emerald-300 via-amber-300 to-blue-300 transform -translate-x-1/2 rounded-full">
          </div>

          <!-- Features -->
          <div class="space-y-8 md:space-y-12 lg:space-y-24">
            <div v-for="(feature, idx) in features" :key="feature.title" class="relative"
              :class="['lg:flex lg:items-center', idx % 2 === 0 ? 'lg:flex-row-reverse' : '']">
              <!-- Mobile/Tablet Layout -->
              <div class="lg:hidden">
                <div class="flex items-start gap-4 group">
                  <!-- Icon -->
                  <div :class="[
                    'flex-shrink-0 w-12 h-12 rounded-xl flex items-center justify-center group-hover:scale-110 transition-transform duration-300',
                    idx % 3 === 0 ? 'bg-emerald-100' : idx % 3 === 1 ? 'bg-amber-100' : 'bg-blue-100'
                  ]">
                    <UIcon :name="feature.icon" :class="[
                      'text-2xl',
                      idx % 3 === 0 ? 'text-emerald-600' : idx % 3 === 1 ? 'text-amber-600' : 'text-blue-600'
                    ]" />
                  </div>

                  <!-- Content -->
                  <div class="flex-1 space-y-2">
                    <h3 class="text-xl md:text-2xl font-bold text-gray-900">
                      {{ feature.title }}
                    </h3>
                    <p class="text-gray-600 leading-relaxed text-sm md:text-base">
                      {{ feature.description }}
                    </p>
                  </div>
                </div>
              </div>

              <!-- Desktop Zigzag Layout -->
              <div class="hidden lg:block lg:w-1/2" :class="idx % 2 === 0 ? 'lg:pr-12 lg:text-right' : 'lg:pl-12'">
                <div class="group hover:scale-105 transition-all duration-300">
                  <div class="space-y-4">
                    <div class="inline-flex items-center gap-3">
                      <div :class="[
                        'w-12 h-12 rounded-xl flex items-center justify-center group-hover:scale-110 transition-transform duration-300',
                        idx % 3 === 0 ? 'bg-emerald-100' : idx % 3 === 1 ? 'bg-amber-100' : 'bg-blue-100'
                      ]">
                        <UIcon :name="feature.icon" :class="[
                          'text-2xl',
                          idx % 3 === 0 ? 'text-emerald-600' : idx % 3 === 1 ? 'text-amber-600' : 'text-blue-600'
                        ]" />
                      </div>
                      <h3 class="text-2xl font-bold text-gray-900">
                        {{ feature.title }}
                      </h3>
                    </div>
                    <p class="text-gray-600 leading-relaxed" :class="idx % 2 === 0 ? 'ml-auto max-w-md' : 'max-w-md'">
                      {{ feature.description }}
                    </p>
                  </div>
                </div>
              </div>

              <!-- Center dot - Desktop only -->
              <div class="hidden lg:block absolute left-1/2 transform -translate-x-1/2 z-10">
                <div :class="[
                  'w-8 h-8 rounded-full border-4 border-white shadow-lg hover:scale-125 transition-all duration-300',
                  idx % 3 === 0 ? 'bg-emerald-500' : idx % 3 === 1 ? 'bg-amber-500' : 'bg-blue-500'
                ]"></div>
              </div>

              <!-- Visual side - Desktop only -->
              <div class="hidden lg:block lg:w-1/2" :class="idx % 2 === 0 ? 'lg:pl-12' : 'lg:pr-12'">
                <div class="relative h-48 rounded-2xl overflow-hidden group">
                  <div class="absolute inset-0 bg-gradient-to-br" :class="[
                    idx % 3 === 0 ? 'from-emerald-400/20 to-emerald-600/20' :
                      idx % 3 === 1 ? 'from-amber-400/20 to-amber-600/20' :
                        'from-blue-400/20 to-blue-600/20'
                  ]"></div>
                  <div class="absolute inset-0 flex items-center justify-center">
                    <div class="text-center space-y-2">
                      <UIcon :name="feature.icon" class="text-6xl opacity-20" :class="[
                        idx % 3 === 0 ? 'text-emerald-600' : idx % 3 === 1 ? 'text-amber-600' : 'text-blue-600'
                      ]" />
                      <div class="text-sm font-medium text-gray-500 uppercase tracking-wider">
                        {{ feature.title.split(' ')[0] }}
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Stats Grid -->
        <div class="mt-12 md:mt-20 lg:mt-32">
          <div class="grid grid-cols-2 lg:grid-cols-4 gap-4 md:gap-6">
            <div v-for="(stat, idx) in stats" :key="stat.label" class="group relative">
              <!-- Background effect -->
              <div
                class="absolute -inset-1 rounded-2xl bg-gradient-to-r opacity-0 group-hover:opacity-100 transition-opacity duration-300"
                :class="[
                  idx % 4 === 0 ? 'from-emerald-400 to-emerald-600' :
                    idx % 4 === 1 ? 'from-amber-400 to-amber-600' :
                      idx % 4 === 2 ? 'from-blue-400 to-blue-600' :
                        'from-purple-400 to-purple-600'
                ]"></div>

              <!-- Card -->
              <div
                class="relative bg-white/90 backdrop-blur-sm rounded-xl md:rounded-2xl p-4 md:p-6 text-center group-hover:shadow-2xl transition-all duration-300 flex flex-col items-center justify-center">
                <!-- Icon -->
                <div class="mb-3 md:mb-4 group-hover:scale-110 transition-transform duration-300">
                  <UIcon
                    :name="idx % 4 === 0 ? 'i-heroicons-arrow-trending-down' : idx % 4 === 1 ? 'i-heroicons-scale' : idx % 4 === 2 ? 'i-heroicons-shield-check' : 'i-heroicons-clock'"
                    class="text-3xl md:text-4xl lg:text-5xl" :class="[
                      idx % 4 === 0 ? 'text-emerald-600' :
                        idx % 4 === 1 ? 'text-amber-600' :
                          idx % 4 === 2 ? 'text-blue-600' :
                            'text-purple-600'
                    ]" />
                </div>

                <!-- Value -->
                <div
                  class="text-2xl md:text-3xl lg:text-4xl font-extrabold text-gray-900 group-hover:scale-110 transition-transform duration-300 mb-1">
                  {{ stat.value }}
                </div>

                <!-- Label -->
                <div
                  class="text-xs md:text-sm font-semibold text-gray-600 group-hover:text-gray-900 transition-colors duration-300">
                  {{ stat.label }}
                </div>

                <!-- Pulse indicator -->
                <div class="absolute top-2 right-2 md:top-3 md:right-3 w-2 h-2 rounded-full animate-pulse" :class="[
                  idx % 4 === 0 ? 'bg-emerald-400' :
                    idx % 4 === 1 ? 'bg-amber-400' :
                      idx % 4 === 2 ? 'bg-blue-400' :
                        'bg-purple-400'
                ]"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>



    <!-- Start Your Journey with Sample Kits Section -->
    <section id="samples" class="py-24 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-12 md:mb-16 lg:mb-20">
          <h2 class="text-2xl sm:text-3xl md:text-4xl lg:text-5xl font-bold text-gray-900 mb-3 md:mb-4 lg:mb-6">
            Start Your Journey with Sample Kits
          </h2>
          <p class="text-base md:text-lg lg:text-xl text-gray-600 max-w-3xl mx-auto px-4">Test quality before you commit
            to
            bulk orders</p>
        </div>

        <div class="grid lg:grid-cols-3 gap-8">
          <div class="bg-white rounded-3xl p-8 border border-gray-100 hover:shadow-xl transition-all duration-300">
            <div class="text-center mb-8">
              <div class="text-4xl font-bold text-emerald-600 mb-2">₹599</div>
              <div class="text-gray-600 font-medium">Starter Kit</div>
            </div>
            <ul class="space-y-4 mb-8">
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm">Basic grade samples</span>
              </li>
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm">2-3 product varieties</span>
              </li>
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm">Basic specifications</span>
              </li>
            </ul>
            <button
              class="w-full bg-emerald-600 hover:bg-emerald-700 text-white py-3 rounded-2xl font-semibold transition-all duration-200 hover:scale-105">
              Order Now
            </button>
          </div>

          <div
            class="bg-white rounded-3xl p-8 border-2 border-emerald-500 relative hover:shadow-xl transition-all duration-300">
            <div class="absolute -top-4 left-1/2 transform -translate-x-1/2">
              <div class="bg-emerald-500 text-white px-4 py-2 rounded-full text-sm font-semibold">
                Most Popular
              </div>
            </div>
            <div class="text-center mb-8">
              <div class="text-4xl font-bold text-emerald-600 mb-2">₹2,999</div>
              <div class="text-gray-600 font-medium">Professional Kit</div>
            </div>
            <ul class="space-y-4 mb-8">
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm">Premium grade samples</span>
              </li>
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm">5-7 product varieties</span>
              </li>
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm">Detailed lab reports</span>
              </li>
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm">Packaging consultation</span>
              </li>
            </ul>
            <button
              class="w-full bg-emerald-600 hover:bg-emerald-700 text-white py-3 rounded-2xl font-semibold transition-all duration-200 hover:scale-105">
              Order Now
            </button>
          </div>

          <div class="bg-white rounded-3xl p-8 border border-gray-100 hover:shadow-xl transition-all duration-300">
            <div class="text-center mb-8">
              <div class="text-4xl font-bold text-emerald-600 mb-2">₹9,999</div>
              <div class="text-gray-600 font-medium">Enterprise Kit</div>
            </div>
            <ul class="space-y-4 mb-8">
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm">Export-grade samples</span>
              </li>
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm">Complete product range</span>
              </li>
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm">Full compliance reports</span>
              </li>
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm">Brand strategy session</span>
              </li>
            </ul>
            <button
              class="w-full bg-emerald-600 hover:bg-emerald-700 text-white py-3 rounded-2xl font-semibold transition-all duration-200 hover:scale-105">
              Order Now
            </button>
          </div>
        </div>
      </div>
    </section>

    <!-- About the Founder Section -->
    <section id="trust" class="py-12 md:py-16 lg:py-24 bg-gray-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid lg:grid-cols-2 gap-8 md:gap-12 lg:gap-16 items-center">
          <div class="space-y-6 md:space-y-8">
            <div class="inline-flex items-center gap-2 bg-emerald-50 border border-emerald-200 rounded-full px-4 py-2">
              <div class="w-2 h-2 bg-emerald-500 rounded-full animate-pulse"></div>
              <span class="text-emerald-700 font-medium text-sm">Our Leadership</span>
            </div>

            <h2 class="text-3xl md:text-4xl lg:text-5xl font-bold text-gray-900 leading-tight">
              Meet Mr. <span
                class="bg-gradient-to-r from-emerald-600 to-emerald-700 bg-clip-text text-transparent">Vivekanand
                Jha</span>
            </h2>

            <div class="space-y-4">
              <div class="flex items-start gap-4">
                <div class="w-8 h-8 bg-emerald-100 rounded-full flex items-center justify-center flex-shrink-0 mt-1">
                  <UIcon name="i-heroicons-academic-cap" class="text-emerald-600" />
                </div>
                <div>
                  <h4 class="font-semibold text-gray-900">Agriculture Expert</h4>
                  <p class="text-gray-600">Years of experience in agricultural sciences and makhana cultivation</p>
                </div>
              </div>

              <div class="flex items-start gap-4">
                <div class="w-8 h-8 bg-emerald-100 rounded-full flex items-center justify-center flex-shrink-0 mt-1">
                  <UIcon name="i-heroicons-shield-check" class="text-emerald-600" />
                </div>
                <div>
                  <h4 class="font-semibold text-gray-900">NRC Certified Advisor</h4>
                  <p class="text-gray-600">National Research Centre certified for agricultural advisory services</p>
                </div>
              </div>

              <div class="flex items-start gap-4">
                <div class="w-8 h-8 bg-emerald-100 rounded-full flex items-center justify-center flex-shrink-0 mt-1">
                  <UIcon name="i-heroicons-briefcase" class="text-emerald-600" />
                </div>
                <div>
                  <h4 class="font-semibold text-gray-900">Former CMO at Rahua Farm</h4>
                  <p class="text-gray-600">Previously served as Chief Marketing Officer at leading agricultural
                    enterprise
                  </p>
                </div>
              </div>
            </div>

            <blockquote class="bg-white rounded-2xl p-4 md:p-6 border border-gray-100">
              <p class="text-base md:text-lg text-gray-700 italic mb-4">"Our legacy is your advantage — from farm to
                business. We
                bring
                decades of makhana expertise directly to your brand success."</p>
              <cite class="text-emerald-600 font-semibold">— Mr. Vivekanand Jha, Founder BMAI</cite>
            </blockquote>
          </div>

          <div class="relative">
            <div
              class="bg-gradient-to-br from-emerald-100 to-amber-100 rounded-3xl p-4 md:p-8 border border-emerald-200">
              <div class="bg-white rounded-2xl p-4 md:p-8 shadow-lg text-center">
                <div
                  class="w-20 h-20 md:w-24 md:h-24 bg-gradient-to-br from-emerald-500 to-emerald-600 rounded-full flex items-center justify-center mx-auto mb-4 md:mb-6">
                  <UIcon name="i-heroicons-user" class="text-white text-3xl md:text-4xl" />
                </div>
                <h3 class="text-xl md:text-2xl font-bold text-gray-900 mb-3 md:mb-4">Visionary Leadership</h3>
                <p class="text-gray-600 leading-relaxed mb-4 md:mb-6">Leading BMAI with passion for quality and
                  commitment
                  to
                  empowering businesses with premium makhana solutions.</p>
                <div class="grid grid-cols-3 gap-2 md:gap-4 text-center">
                  <div>
                    <div class="text-xl md:text-2xl font-bold text-emerald-600">30+</div>
                    <div class="text-xs text-gray-600">Brands Trusted</div>
                  </div>
                  <div>
                    <div class="text-xl md:text-2xl font-bold text-amber-600">15+</div>
                    <div class="text-xs text-gray-600">Years Experience</div>
                  </div>
                  <div>
                    <div class="text-xl md:text-2xl font-bold text-blue-600">100%</div>
                    <div class="text-xs text-gray-600">Success Rate</div>
                  </div>
                </div>
              </div>
            </div>
            <div
              class="absolute -bottom-4 -right-4 md:-bottom-8 md:-right-8 w-24 h-24 md:w-32 md:h-32 bg-emerald-200 rounded-full blur-3xl opacity-30 -z-10">
            </div>
            <div
              class="absolute -top-4 -left-4 md:-top-8 md:-left-8 w-24 h-24 md:w-32 md:h-32 bg-amber-200 rounded-full blur-3xl opacity-30 -z-10">
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- testomonial section  -->

    <!-- Testimonials Section -->
    <section class="py-24 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-8 md:mb-12 lg:mb-16">
          <h2 class="text-2xl sm:text-3xl md:text-4xl lg:text-5xl font-bold text-gray-900 mb-2 md:mb-4">
            Trusted by Businesses Like Yours
          </h2>
          <p class="text-sm sm:text-base md:text-lg text-gray-600 max-w-2xl mx-auto px-4">
            See what our partners say about working with BMAI
          </p>
        </div>

        <div class="grid md:grid-cols-3 gap-8">
          <!-- Testimonial 1 -->
          <div class="bg-gray-50 rounded-2xl p-8 border border-gray-100 hover:shadow-lg transition-all duration-300">
            <div class="flex items-center mb-6">
              <div class="w-12 h-12 bg-emerald-100 rounded-full flex items-center justify-center mr-4">
                <UIcon name="i-heroicons-user" class="text-emerald-600 text-xl" />
              </div>
              <div>
                <h4 class="font-semibold text-gray-900">Rajesh Kumar</h4>
                <p class="text-sm text-gray-600">Wholesaler, Delhi</p>
              </div>
            </div>
            <div class="mb-4">
              <div class="flex text-amber-400">
                <UIcon name="i-heroicons-star-solid" class="text-lg" />
                <UIcon name="i-heroicons-star-solid" class="text-lg" />
                <UIcon name="i-heroicons-star-solid" class="text-lg" />
                <UIcon name="i-heroicons-star-solid" class="text-lg" />
                <UIcon name="i-heroicons-star-solid" class="text-lg" />
              </div>
            </div>
            <p class="text-gray-700 italic">
              "BMAI's consistent quality and reliable delivery has helped us grow our makhana business by 40% this year.
              Their transparent pricing is unmatched."
            </p>
          </div>

          <!-- Testimonial 2 -->
          <div class="bg-gray-50 rounded-2xl p-8 border border-gray-100 hover:shadow-lg transition-all duration-300">
            <div class="flex items-center mb-6">
              <div class="w-12 h-12 bg-blue-100 rounded-full flex items-center justify-center mr-4">
                <UIcon name="i-heroicons-user" class="text-blue-600 text-xl" />
              </div>
              <div>
                <h4 class="font-semibold text-gray-900">Priya Sharma</h4>
                <p class="text-sm text-gray-600">Private Label Owner, Mumbai</p>
              </div>
            </div>
            <div class="mb-4">
              <div class="flex text-amber-400">
                <UIcon name="i-heroicons-star-solid" class="text-lg" />
                <UIcon name="i-heroicons-star-solid" class="text-lg" />
                <UIcon name="i-heroicons-star-solid" class="text-lg" />
                <UIcon name="i-heroicons-star-solid" class="text-lg" />
                <UIcon name="i-heroicons-star-solid" class="text-lg" />
              </div>
            </div>
            <p class="text-gray-700 italic">
              "The sample kit helped us perfect our recipe before launch. BMAI's end-to-end support made starting our
              brand incredibly smooth and risk-free."
            </p>
          </div>

          <!-- Testimonial 3 -->
          <div class="bg-gray-50 rounded-2xl p-8 border border-gray-100 hover:shadow-lg transition-all duration-300">
            <div class="flex items-center mb-6">
              <div class="w-12 h-12 bg-amber-100 rounded-full flex items-center justify-center mr-4">
                <UIcon name="i-heroicons-user" class="text-amber-600 text-xl" />
              </div>
              <div>
                <h4 class="font-semibold text-gray-900">Amit Patel</h4>
                <p class="text-sm text-gray-600">Retailer, Bangalore</p>
              </div>
            </div>
            <div class="mb-4">
              <div class="flex text-amber-400">
                <UIcon name="i-heroicons-star-solid" class="text-lg" />
                <UIcon name="i-heroicons-star-solid" class="text-lg" />
                <UIcon name="i-heroicons-star-solid" class="text-lg" />
                <UIcon name="i-heroicons-star-solid" class="text-lg" />
                <UIcon name="i-heroicons-star-solid" class="text-lg" />
              </div>
            </div>
            <p class="text-gray-700 italic">
              "Live video processing gave us complete confidence in quality. Our customers love the premium makhana we
              source through BMAI."
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <footer class="bg-gray-100 text-black">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
        <div class="grid md:grid-cols-4 gap-8">
          <!-- Brand -->
          <div>
            <div class="flex items-center gap-3 mb-4">
              <img src="../assets/imgs/logo.png" alt="" class="w-18 h-18">
              <span class="text-2xl font-bold">BMAI</span>
            </div>
            <p class="text-gray-400 text-sm">Your trusted makhana partner from Bihar to shelf.</p>
          </div>

          <!-- Quick Links -->
          <div>
            <h4 class="font-semibold mb-4">Quick Links</h4>
            <ul class="space-y-2 text-sm text-gray-400">
              <li><button @click="scrollTo('services')" class="hover:text-white transition-colors">Services</button>
              </li>
              <li><button @click="scrollTo('process')" class="hover:text-white transition-colors">Process</button></li>
              <li><button @click="scrollTo('samples')" class="hover:text-white transition-colors">Samples</button></li>
              <li><button @click="scrollTo('contact')" class="hover:text-white transition-colors">Contact</button></li>
            </ul>
          </div>

          <!-- Products -->
          <div>
            <h4 class="font-semibold mb-4">Products</h4>
            <ul class="space-y-2 text-sm text-gray-400">
              <li><span class="hover:text-white transition-colors cursor-pointer">Premium Makhana</span></li>
              <li><span class="hover:text-white transition-colors cursor-pointer">Flavored Varieties</span></li>
              <li><span class="hover:text-white transition-colors cursor-pointer">Bulk Supply</span></li>
              <li><span class="hover:text-white transition-colors cursor-pointer">Private Label</span></li>
            </ul>
          </div>

          <!-- Contact -->
          <div>
            <h4 class="font-semibold mb-4">Get in Touch</h4>
            <ul class="space-y-2 text-sm text-gray-400">
              <li class="flex items-center gap-2">
                <UIcon name="i-heroicons-phone" class="text-emerald-400" />
                <span>+91 XXXXX XXXXX</span>
              </li>
              <li class="flex items-center gap-2">
                <UIcon name="i-heroicons-envelope" class="text-emerald-400" />
                <span>hello@bmai.com</span>
              </li>
              <li class="flex items-center gap-2">
                <UIcon name="i-heroicons-map-pin" class="text-emerald-400" />
                <span>Bihar, India</span>
              </li>
            </ul>
          </div>
        </div>

        <!-- Bottom Bar -->
        <div class="border-t border-gray-200 mt-12 pt-8 text-center text-sm text-gray-400">
          <p>&copy; {{ new Date().getFullYear() }} BMAI. All rights reserved.</p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const mobileOpen = ref(false)

const items = ref([
  {
    title: 'Market Consultation',
    description: 'Free expert guidance from our NRC certified advisors',
    icon: 'i-lucide-users'
  },
  {
    title: 'Sample Testing',
    description: 'Test our makhana quality before committing',
    icon: 'i-lucide-package'
  },
  {
    title: 'Transparent Processing',
    description: 'Live video processing from Bihar to your location',
    icon: 'i-lucide-video'
  },
  {
    title: 'Delivery & Support',
    description: 'Reliable delivery with ongoing business support',
    icon: 'i-lucide-truck'
  }
])

const scrollTo = (id) => {
  const element = document.getElementById(id)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}

const formData = ref({
  name: '',
  business: '',
  phone: '',
  email: '',
  needs: [],
  interests: []
})

const handleSubmit = (e) => {
  e.preventDefault()
  // Add your form submission logic here
  console.log('Form submitted:', formData.value)
}

const features = [
  {
    icon: 'i-heroicons-star-solid',
    title: 'Trusted by 30+ Brands',
    description: 'Proven track record of success with established and emerging private label brands'
  },
  {
    icon: 'i-heroicons-beaker-solid',
    title: 'Samples from ₹599',
    description: 'Test quality before committing with our flexible and adjustable sample options'
  },
  {
    icon: 'i-heroicons-video-camera-solid',
    title: 'Transparent Processing',
    description: 'Live video processing from Bihar to Noida/Delhi for complete visibility'
  },
  {
    icon: 'i-heroicons-shield-check-solid',
    title: 'Hygienic Packing',
    description: 'Modern facilities ensuring food safety standards and quality control'
  },
  {
    icon: 'i-heroicons-clock-solid',
    title: 'Quick Turnaround',
    description: 'Fast processing and delivery to keep your business moving forward'
  },
  {
    icon: 'i-heroicons-currency-rupee-solid',
    title: 'Competitive Pricing',
    description: 'Best rates with transparent pricing and volume discounts available'
  }
];



const stats = [
  { value: '30+', label: 'Partner Brands' },
  { value: '500+', label: 'Tons Monthly' },
  { value: '100%', label: 'Quality Assured' },
  { value: '24/7', label: 'Support Available' }
];

const active = ref(0)

// Note: This is for demonstration purposes only. Don't do this at home.
onMounted(() => {
  setInterval(() => {
    active.value = (active.value + 1) % items.value.length
  }, 2000)
})


const isMdAndSm = computed(() => {
  return window.innerWidth <= 768
})

</script>

<style scoped>
.hover\:scale-105:hover {
  transform: scale(1.05);
}

.transition-all {
  transition: all 0.3s ease;
}

.transition-colors {
  transition: color 0.2s ease, background-color 0.2s ease, border-color 0.2s ease;
}

html {
  scroll-behavior: smooth;
}

button:focus-visible {
  outline: 2px solid #059669;
  outline-offset: 2px;
}
</style>