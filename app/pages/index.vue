<template>
  <div class="min-h-screen bg-white">

    <!-- Modern Navigation -->
    <nav class="fixed top-0 left-0 right-0 bg-white/95 backdrop-blur-lg border-b border-gray-100 z-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center h-14 md:h-20">
          <div class="flex items-center gap-2">
            <img src="../assets/imgs/logo.png" alt="" class="w-14 h-14 object-cover">
            <div class="flex flex-col items-start">
              <span class="text-md  font-bold text-gray-900">Bihar Makhana</span>
              <span class="text-md font-bold text-gray-900">Agro Industries</span>
            </div>
          </div>
          <div class="hidden md:flex items-center gap-8">
            <button @click="scrollTo('who-we-serve')"
              class="text-gray-600 hover:text-emerald-600 transition-colors font-medium">Services</button>
            <button @click="scrollTo('samples')"
              class="text-gray-600 hover:text-emerald-600 transition-colors font-medium">Kit</button>
            <button @click="scrollTo('trust')"
              class="text-gray-600 hover:text-emerald-600 transition-colors font-medium">About</button>
            <button @click="scrollTo('contact')"
              class="text-gray-600 hover:text-emerald-600 transition-colors font-medium">Contact</button>
            <button @click="scrollTo('media')"
              class="text-gray-600 hover:text-emerald-600 transition-colors font-medium">Media</button>
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
    <section class="min-h-[calc(100dvh-80px)] pt-20 -mt-4 md:mt-16 px-4 flex items-center py-4 sm:py-4 md:py-4">
      <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid lg:grid-cols-2 md:gap-10 lg:gap-16 items-center">
          <div class="lg:hidden relative mb-6 md:mb-8 mt-4 md:mt-0">
            <img
              src="../assets/imgs/makhana-boat.jpg"
              alt="Makhana bowl" class="w-full h-64 md:h-56 object-cover rounded-2xl" />
            
          </div>

          <div class="space-y-4 md:space-y-4">
            <div class="space-y-2 md:space-y-3">
              <h1 class="text-3xl md:text-4xl lg:text-5xl font-bold text-gray-900 leading-tight">
                Reliable <span class="text-emerald-600">Makhana</span> <br class="hidden lg:block" /> Sourcing.
              </h1>
              <h2 class="text-lg md:text-xl lg:text-2xl font-medium text-gray-700 leading-relaxed">
                Built for Brands & Enterprises That Care About Quality.
              </h2>
            </div>

            <div class="flex flex-wrap gap-2">
              <UBadge label="Consistent Quality" color="success" variant="soft" size="md"
                icon="i-heroicons-check-circle"
                class="rounded-full font-semibold uppercase tracking-wider text-[10px] md:text-xs" />
              <UBadge label="Market-Aligned Grades" color="success" variant="soft" size="md"
                icon="i-heroicons-check-circle"
                class="rounded-full font-semibold uppercase tracking-wider text-[10px] md:text-xs" />
              <UBadge label="Reliable Supply Chain" color="success" variant="soft" size="md"
                icon="i-heroicons-check-circle"
                class="rounded-full font-semibold uppercase tracking-wider text-[10px] md:text-xs" />
            </div>

            <div class="flex flex-col sm:flex-row gap-3 md:gap-4">
              <UButton @click="scrollTo('contact')" color="success" variant="solid" icon="i-heroicons-phone"
                class="px-6 py-3 text-sm md:text-base font-semibold shadow-sm justify-center">
                Talk to Our Sourcing Expert
              </UButton>
              <UButton @click="scrollTo('samples')" color="success" variant="ghost"
                icon="i-heroicons-clipboard-document"
                class="px-6 py-3 text-sm md:text-base font-semibold justify-center">
                Request Sample
              </UButton>
            </div>
          </div>

          <div class="relative hidden lg:block order-1 lg:order-2 group align-center">
            <div
              class="absolute -inset-2 bg-emerald-200/30 rounded-2xl blur-xl group-hover:bg-emerald-300/40 transition-all duration-700">
            </div>
            <div class="relative">
              <img src="../assets/imgs/makhana-boat.jpg" alt="Premium Makhana Production"
                class="w-full aspect-[4/5] lg:aspect-[4/4] object-cover rounded-2xl shadow-xl border-2 border-white" />
              <div
                class="absolute -bottom-3 left-1/2 -translate-x-1/2 lg:left-0 lg:translate-x-[-10%] bg-white p-2 rounded-lg shadow-lg border border-emerald-50 flex items-center gap-2 min-w-[160px]">
                <div class="w-8 h-8 bg-emerald-500 rounded-full flex items-center justify-center flex-shrink-0">
                  <UIcon name="i-heroicons-sparkles" class="text-white text-lg" />
                </div>
                <div>
                  <p class="text-xs font-bold text-gray-900">500+ Businesses</p>
                  <p class="text-[9px] text-gray-500">Trusted across India</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- problems -->

    <!-- Pain Points / Problems Section -->
    <section id="problems" class="py-24 bg-gradient-to-br from-emerald-50 to-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
          <UBadge color="emerald" variant="subtle" size="lg" class="mb-4" icon="i-heroicons-exclamation-triangle">
            The Sourcing Reality
          </UBadge>
          <h2 class="text-3xl md:text-4xl lg:text-5xl font-bold text-gray-900 mb-4 md:mb-6">
            Why Sourcing Makhana Is Still a Challenge
          </h2>
          <p class="text-sm sm:text-base md:text-lg text-gray-600 max-w-3xl mx-auto">
            Hidden inefficiencies in the supply chain can damage your brand credibility and shrink your margins.
          </p>
        </div>

        <div class="grid lg:grid-cols-2 gap-6 md:gap-8 lg:gap-12 items-center">

          <!-- Image Grid -->
          <div class="grid grid-cols-2 gap-3 md:gap-4">
            <div class="space-y-3 md:space-y-4">
              <div
                class="rounded-2xl overflow-hidden shadow-lg border-2 border-white hover:border-emerald-300 transition-all">
                <img src="../assets/imgs/p-1.png" alt="Quality Issues" class="w-full  object-contain" />
              </div>
              <div
                class="rounded-2xl overflow-hidden shadow-lg border-2 border-white hover:border-emerald-300 transition-all">
                <img src="../assets/imgs/p-2.png" alt="Packaging Waste" class="w-full object-contain" />
              </div>
            </div>

            <div class="space-y-3 md:space-y-4 pt-6 md:pt-8">
              <div
                class="rounded-2xl overflow-hidden shadow-lg border-2 border-white hover:border-emerald-300 transition-all">
                <img src="../assets/imgs/p-3.png" alt="Supply Chain Gaps" class="w-full object-contain" />
              </div>
              <div
                class="rounded-2xl overflow-hidden shadow-lg border-2 border-white hover:border-emerald-300 transition-all">
                <img src="../assets/imgs/p-4.png" alt="Price Volatility" class="w-full object-contain" />
              </div>
            </div>
          </div>

          <!-- Problems List -->
          <div class="grid sm:grid-cols-1 gap-4 md:gap-6 mt-6 md:mt-0">
            <div v-for="(item, index) in problems" :key="index"
              class="group flex gap-3 md:gap-4 p-4 md:p-6 bg-white/50 backdrop-blur-sm rounded-2xl border border-emerald-100 hover:bg-white hover:shadow-xl transition-all duration-300">
              <div
                class="flex-shrink-0 w-10 h-10 md:w-12 md:h-12 bg-emerald-100 rounded-xl flex items-center justify-center group-hover:bg-emerald-500 transition-colors duration-300">
                <UIcon :name="item.icon" class="text-emerald-600 group-hover:text-white text-xl md:text-2xl" />
              </div>
              <div>
                <h3 class="text-base md:text-lg font-bold text-gray-900">{{ item.title }}</h3>
                <p class="text-xs md:text-sm text-gray-600">{{ item.description }}</p>
              </div>
            </div>
          </div>
        </div>

        <div class="mt-20">
          <div
            class="shadow-2xl rounded-2xl transition-all duration-300 border border-neutral-300 rounded-3xl text-black relative overflow-hidden grid lg:grid-cols-2 items-center">
            <!-- Left: Image -->
            <div class="relative h-64 lg:h-full">
              <img src="../assets/imgs/cta-hero.png" alt="Reliable Makhana Supply"
                class="absolute inset-0 w-full h-full object-cover">
              <!-- Gradient overlay for readability -->
            </div>

            <!-- Right: Content -->
            <div class="relative z-10 p-8 md:p-12">
              <UBadge color="emerald" variant="subtle" size="lg" class="mb-4" icon="i-heroicons-light-bulb">
                Ready to Eliminate These Pain Points?
              </UBadge>
              <h3 class="text-2xl md:text-3xl font-bold mb-4">
                Join 500+ businesses who've secured their supply chain
              </h3>
              <p class="mb-8">
                Experience the reliability of our standardized grading system and never worry about quality again.
              </p>
              <div class="flex flex-wrap gap-4 justify-center">
                <UButton @click="scrollTo('contact')" color="success" size="xl" class="font-bold px-8">
                  Get Risk-Free Consultation
                </UButton>
                <UButton variant="ghost" color="white" size="xl" icon="i-heroicons-phone">
                  Call Expert
                </UButton>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>



    <!-- Who We Serve Section -->
    <section class="py-8 pb-24 bg-gradient-to-b from-gray-50 to-white" id="who-we-serve">
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
          <!-- Enterprises -->
          <div class="group shadow-2xl p-8 rounded-2xl transition-all duration-300 border border-neutral-300">
            <div class="space-y-6">
              <!-- Icon -->
              <div
                class="inline-flex p-4 bg-success-500 rounded-xl group-hover:scale-110 transition-transform duration-300">
                <UIcon name="i-heroicons-building-office-2" class="text-white text-3xl" />
              </div>

              <!-- Title & Stats -->
              <div>
                <h3 class="text-2xl font-bold text-gray-900 mb-2">Enterprises</h3>
                <UBadge color="success" variant="subtle" icon="i-heroicons-check-circle-solid">100+ Tons Monthly
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

          <!-- Wholesalers -->
          <div
            class="group shadow-2xl p-8 rounded-2xl transition-all duration-300 border border-gray-100 border-neutral-300">
            <div class="space-y-6">
              <!-- Icon -->
              <div
                class="inline-flex p-4 bg-info-500 rounded-xl group-hover:scale-110 transition-transform duration-300">
                <UIcon name="i-heroicons-building-storefront" class="text-white text-3xl" />
              </div>

              <!-- Title & Stats -->
              <div>
                <h3 class="text-2xl font-bold text-gray-900 mb-2">Wholesalers</h3>
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
                Explore Wholesale Options
              </UButton>
            </div>
          </div>



          <!-- Brands -->

          <div class="group shadow-2xl p-8 rounded-2xl transition-all duration-300 border border-neutral-300">
            <div class="space-y-6">
              <!-- Icon -->
              <div
                class="inline-flex p-4 bg-warning-500 rounded-xl group-hover:scale-110 transition-transform duration-300">
                <UIcon name="i-heroicons-sparkles" class="text-white text-3xl" />
              </div>

              <!-- Title & Stats -->
              <div>
                <h3 class="text-2xl font-bold text-gray-900 mb-2">Brands</h3>
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
                Launch Your Brand
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
    <section class="py-12 md:py-16 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-10">
          <h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-3">
            Why Choose BMAI
          </h2>
          <p class="text-base text-gray-600 max-w-xl mx-auto">
            Trusted expertise from Bihar's makhana heartland to your business success.
          </p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 mb-16">
          <div v-for="(feature, idx) in features" :key="feature.title"
            class="group p-6 rounded-2xl border border-gray-100 bg-gray-50 hover:bg-white hover:shadow-xl hover:shadow-gray-200/50 transition-all duration-300">

            <div class="flex items-center gap-4 mb-4">
              <div :class="[
                'w-10 h-10 rounded-lg flex items-center justify-center shrink-0',
                idx % 3 === 0 ? 'bg-emerald-100 text-emerald-600' : idx % 3 === 1 ? 'bg-amber-100 text-amber-600' : 'bg-blue-100 text-blue-600'
              ]">
                <UIcon :name="feature.icon" class="text-xl" />
              </div>
              <h3 class="font-bold text-gray-900 leading-tight">
                {{ feature.title }}
              </h3>
            </div>

            <p class="text-sm text-gray-600 leading-relaxed">
              {{ feature.description }}
            </p>
          </div>
        </div>

        <div class="grid grid-cols-2 md:grid-cols-4 gap-4 border-t border-gray-100 pt-12">
          <div v-for="(stat, idx) in stats" :key="stat.label" class="text-center px-4">
            <div :class="[
              'text-2xl md:text-3xl font-extrabold mb-1',
              idx % 4 === 0 ? 'text-emerald-600' : idx % 4 === 1 ? 'text-amber-600' : idx % 4 === 2 ? 'text-blue-600' : 'text-purple-600'
            ]">
              {{ stat.value }}
            </div>
            <div class="text-xs font-bold uppercase tracking-wider text-gray-500">
              {{ stat.label }}
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
            Start Your Makhana Journey with the Right Entry Plan
          </h2>
          <p class="text-base md:text-lg lg:text-xl text-gray-600 max-w-3xl mx-auto px-4">
            Industry-ready starter kits designed for brands & enterprises planning to enter or scale in the makhana
            business.
          </p>
        </div>

        <div class="grid lg:grid-cols-3 gap-8">
          <!-- ₹599 Industry Starter Sample Kit -->
          <div class="bg-white rounded-3xl p-8 border border-gray-100 hover:shadow-xl transition-all duration-300">
            <div class="text-center mb-8">
              <div class="text-4xl font-bold text-emerald-600 mb-2">₹599</div>
              <div class="text-gray-600 font-medium">Industry Starter Sample Kit</div>
            </div>
            <div class="mb-6">
              <p class=" text-center text-sm text-gray-600">First-time explorers & early-stage research</p>
            </div>
            <ul class="space-y-4 mb-8">
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm">Total <strong>500 g sample kit</strong> (10 variants × 50 g each —
                  assorted grades)</span>
              </li>
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm">Helps understand <strong>size, quality & grading
                    differences</strong></span>
              </li>
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm">Ideal for <strong>basic product evaluation & internal
                    testing</strong></span>
              </li>
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm"><strong>Price includes GST & transport</strong></span>
              </li>
            </ul>
            <button
              class="w-full bg-emerald-600 hover:bg-emerald-700 text-white py-3 rounded-2xl font-semibold transition-all duration-200 hover:scale-105">
              Get Starter Samples
            </button>
          </div>

          <!-- ₹2,999 Brand Launch Preparation Kit -->
          <div
            class="bg-white rounded-3xl p-8 border-2 border-emerald-500 relative hover:shadow-xl transition-all duration-300">
            <div class="absolute -top-4 left-1/2 transform -translate-x-1/2">
              <div class="bg-emerald-500 text-white px-4 py-2 rounded-full text-sm font-semibold">
                Most Popular
              </div>
            </div>
            <div class="text-center mb-8">
              <div class="text-4xl font-bold text-emerald-600 mb-2">₹2,999</div>
              <div class="text-gray-600 font-medium">Brand Launch & Strategy Kit</div>
            </div>
            <div class="mb-6">
              <p class="text-center text-sm text-gray-600">Brands planning market entry or private labels</p>
            </div>
            <ul class="space-y-4 mb-8">
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm"><strong>1.5 kg customised sample kit</strong> (weights & grades
                  tailored
                  to your target market)</span>
              </li>
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm"><strong>1-on-1 consultancy (4 hours)</strong></span>
              </li>
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm">Market insights & category-level research data</span>
              </li>
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm">Packaging & grade-selection guidance</span>
              </li>
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm">Opportunity discussion to enter the makhana segment
                  strategically</span>
              </li>
            </ul>
            <button
              class="w-full bg-emerald-600 hover:bg-emerald-700 text-white py-3 rounded-2xl font-semibold transition-all duration-200 hover:scale-105">
              Book Consultation & Samples
            </button>
          </div>

          <!-- ₹9,999 Enterprise Entry & Strategy Kit -->
          <div class="bg-white rounded-3xl p-8 border border-gray-100 hover:shadow-xl transition-all duration-300">
            <div class="text-center mb-8">
              <div class="text-4xl font-bold text-emerald-600 mb-2">₹9,999</div>
              <div class="text-gray-600 font-medium">Enterprise Market Entry Kit</div>
            </div>
            <div class="mb-6">
              <p class="text-center text-sm text-gray-600">Enterprises, distributors & serious market entrants</p>
            </div>
            <ul class="space-y-4 mb-8">
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm"><strong>7 kg comprehensive sample kit</strong></span>
              </li>
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm"><strong>1-on-1 strategic discussion (10 hours)</strong></span>
              </li>
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm">Processed & curated <strong>market-specific client
                    data</strong></span>
              </li>
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm">Supply chain & sourcing clarity</span>
              </li>
              <li class="flex items-start gap-3">
                <UIcon name="i-heroicons-check" class="text-emerald-500 flex-shrink-0 mt-1" />
                <span class="text-gray-700 text-sm">Business readiness support to confidently start operations</span>
              </li>
            </ul>
            <button
              class="w-full bg-emerald-600 hover:bg-emerald-700 text-white py-3 rounded-2xl font-semibold transition-all duration-200 hover:scale-105">
              Start with Enterprise Support
            </button>
          </div>
        </div>

        <!-- Supporting Line -->
        <div class="mt-16 text-center">
          <p class="text-gray-600 mb-4">From product understanding to market entry strategy—choose the level of support
            you
            need.</p>
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

    <!-- Media / Gallery Section -->
    <section id="media" class="py-24 bg-gray-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-12 md:mb-16">
          <h2 class="text-2xl sm:text-3xl md:text-4xl lg:text-5xl font-bold text-gray-900 mb-3 md:mb-4">
            See Our Makhana Journey
          </h2>
          <p class="text-base md:text-lg text-gray-600 max-w-2xl mx-auto">
            From harvest to your shelf—transparent processing you can trust
          </p>
        </div>

        <!-- Image Grid -->
        <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4 md:gap-6">
          <div v-for="(img, i) in gallery" :key="i"
            class="group relative rounded-2xl overflow-hidden shadow hover:shadow-xl transition-all duration-300 cursor-pointer">
            <img :src="img.src" :alt="img.alt"
              class="w-full h-48 md:h-56 object-contain group-hover:scale-105 transition-transform duration-300" />
            <div
              class="absolute inset-0 bg-gradient-to-t from-black/50 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-end p-4">
              <p class="text-white text-sm font-medium">{{ img.caption }}</p>
            </div>
          </div>
        </div>


      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-24 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-12 md:mb-16">
          <h2 class="text-3xl md:text-4xl lg:text-5xl font-bold text-gray-900 mb-4">
            Get in Touch
          </h2>
          <p class="text-lg text-gray-600 max-w-2xl mx-auto">
            Ready to start your makhana journey? Reach out for samples, pricing, or any questions.
          </p>
        </div>

        <div class="">

          <!-- Contact Info & Map -->
          <div class="space-y-6 max-w-2xl mx-auto">
            <!-- Contact Cards -->
            <div class="grid md:grid-cols-2 gap-3">
              <div class="bg-emerald-50 rounded-lg p-4 border border-emerald-200">
                <div class="flex items-center gap-2 mb-2">
                  <div class="w-8 h-8 bg-emerald-100 rounded-md flex items-center justify-center">
                    <UIcon name="i-heroicons-phone" class="text-emerald-600" />
                  </div>
                  <h3 class="font-semibold text-gray-900 text-sm">Call Us</h3>
                </div>
                <a href="tel:+919876543210" class="text-emerald-600 font-medium text-sm hover:underline">
                  +91 98765 43210
                </a>
                <p class="text-xs text-gray-600 mt-1">Mon-Sat, 9AM-6PM IST</p>
              </div>

              <div class="bg-blue-50 rounded-lg p-4 border border-blue-200">
                <div class="flex items-center gap-2 mb-2">
                  <div class="w-8 h-8 bg-blue-100 rounded-md flex items-center justify-center">
                    <UIcon name="i-heroicons-envelope" class="text-blue-600" />
                  </div>
                  <h3 class="font-semibold text-gray-900 text-sm">Email Us</h3>
                </div>
                <a href="mailto:hello@bmai.com" class="text-blue-600 font-medium text-sm hover:underline">
                  hello@bmai.com
                </a>
                <p class="text-xs text-gray-600 mt-1">We reply within 24 hours</p>
              </div>
            </div>

            <!-- Location -->
            <div class="bg-gray-50 rounded-lg p-4 border border-gray-200">
              <div class="flex items-center gap-2 mb-2">
                <div class="w-8 h-8 bg-gray-100 rounded-md flex items-center justify-center">
                  <UIcon name="i-heroicons-map-pin" class="text-gray-600" />
                </div>
                <h3 class="font-semibold text-gray-900 text-sm">Visit Us</h3>
              </div>
              <p class="text-gray-700 text-sm leading-relaxed">
                BMAI Processing Unit<br />
                Industrial Area, Darbhanga<br />
                Bihar, India - 846004
              </p>
            </div>

            <!-- Social Links -->
            <div class="flex gap-3 justify-center">
              <a href="#"
                class="w-10 h-10 bg-gray-100 rounded-lg flex items-center justify-center hover:bg-emerald-100 hover:text-emerald-600 transition-all duration-200"
                aria-label="WhatsApp">
                <UIcon name="i-mdi-whatsapp" class="text-lg" />
              </a>
              <a href="#"
                class="w-10 h-10 bg-gray-100 rounded-lg flex items-center justify-center hover:bg-blue-100 hover:text-blue-600 transition-all duration-200"
                aria-label="LinkedIn">
                <UIcon name="i-mdi-linkedin" class="text-lg" />
              </a>
              <a href="#"
                class="w-10 h-10 bg-gray-100 rounded-lg flex items-center justify-center hover:bg-pink-100 hover:text-pink-600 transition-all duration-200"
                aria-label="Instagram">
                <UIcon name="i-mdi-instagram" class="text-lg" />
              </a>
            </div>
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

useHead({
  title: 'BMAI - Premium Makhana from Bihar to shelf',
  meta: [
    { name: 'description', content: 'BMAI offers premium makhana from Bihar to shelf with transparent processing, samples testing, and market consultation.' }
  ]
})

import { ref } from 'vue'
const mobileOpen = ref(false)
const gallery = [
  {
    src: '/media/1.jpeg',
    alt: 'img',
  },
  {
    src: '/media/2.jpeg',
    alt: 'img',
  },
  {
    src: '/media/3.jpeg',
    alt: 'img',
  },
  {
    src: '/media/4.jpeg',
    alt: 'img',
  },
  {
    src: '/media/5.jpeg',
    alt: 'img',
  },
  {
    src: '/media/6.jpeg',
    alt: 'img',
  },
  {
    src: '/media/7.jpeg',
    alt: 'img',
  },
  {
    src: '/media/8.jpeg',
    alt: 'img',
  },
  {
    src: '/media/9.jpeg',
    alt: 'img',
  },
  {
    src: '/media/10.jpeg',
    alt: 'img',
  },
  {
    src: '/media/11.jpeg',
    alt: 'img',
  },
  {
    src: '/media/12.jpeg',
    alt: 'img',
  },
  {
    src: '/media/13.jpeg',
    alt: 'img',
  },
]
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

const problems = [
  {
    title: "Quality & Grading Uncertainty",
    description: "No standardized grading leads to inconsistent batches and customer complaints.",
    icon: "i-heroicons-beaker"
  },
  {
    title: "High Packaging Waste",
    description: "Wrong size selection increases your packaging costs by up to 30%.",
    icon: "i-heroicons-scissors"
  },
  {
    title: "Contamination & Brand Risk",
    description: "Poor storage and handling risks moisture damage and contamination.",
    icon: "i-heroicons-shield-check"
  },
  {
    title: "Supply Chain Gaps",
    description: "Inconsistent delivery schedules disrupt your production and retail shelf presence.",
    icon: "i-heroicons-arrows-right-left"
  }
]

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
  { value: '100+', label: 'Tons Monthly' },
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