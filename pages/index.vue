<template>
  <div class="min-h-screen w-full font-sans overflow-x-hidden">
    <!-- Header -->
    <header
  :class="[
    'fixed inset-x-0 top-0 z-40 transition-colors duration-300',
    scrolled ? 'bg-gradient-to-r from-[#42389E] to-[#1A1C3D] shadow-md' : 'bg-transparent'
  ]"
>
      <nav class="max-w-screen-xl mx-auto px-4">
        <div class="flex items-center justify-between h-16">
          <!-- Logo -->
          <div class="shrink-0">
            <div class="flex items-center">
              <img src="/logo.png" alt="IntelliToggle" class="w-15 h-10"></img>
            </div>
          </div>

          <!-- Desktop Navigation -->
          <div class="hidden md:flex ml-10">
            <div class="flex items-center gap-8">
              <a
                href="#home"
                class="text-white text-sm font-medium py-2 border-b-2 border-transparent hover:border-white transition"
                >Home</a
              >
              <a
                href="#about"
                class="text-gray-300 text-sm font-medium py-2 border-b-2 border-transparent hover:border-white transition"
                >About</a
              >
              <a
                href="#pricing"
                class="text-gray-300 text-sm font-medium py-2 border-b-2 border-transparent hover:border-white transition"
                >Pricing</a
              >
            </div>
          </div>

          <!-- Desktop CTA -->
          <div class="hidden md:flex items-center gap-3">
            <button
              class="bg-[#F9A71E] text-black px-3 py-2 rounded-md text-sm font-semibold hover:bg-orange-500 transition"
            >
            <span style="background-image: linear-gradient(180deg, #42389E, #0F1026); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;">Start Sandbox</span>
            </button>
          </div>

          <!-- Mobile menu button -->
          <button
            @click="toggleMobileMenu"
            class="md:hidden text-white p-2"
            aria-label="Toggle menu"
          >
            <svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path
                v-if="!isMobileMenuOpen"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16"
              />
              <path
                v-else
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>
        </div>

        <!-- Mobile Navigation -->
        <div
          v-if="isMobileMenuOpen"
          class="fixed top-0 right-0 h-screen w-80 bg-white shadow-xl z-50 transition-transform"
        >
          <div class="p-6">
            <div class="flex justify-end mb-6">
              <button @click="closeMobileMenu" class="text-gray-500" aria-label="Close menu">
                <svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                </svg>
              </button>
            </div>

            <nav class="mb-6">
              <a
                href="#home"
                @click="closeMobileMenu"
                class="block text-gray-900 p-3 rounded-md text-lg font-medium mb-2"
                >Home</a
              >
              <a
                href="#features"
                @click="closeMobileMenu"
                class="block text-gray-500 p-3 rounded-md text-lg font-medium mb-2"
                >Features</a
              >
              <a
                href="#pricing"
                @click="closeMobileMenu"
                class="block text-gray-500 p-3 rounded-md text-lg font-medium mb-2"
                >Pricing</a
              >
              <a
                href="#about"
                @click="closeMobileMenu"
                class="block text-gray-500 p-3 rounded-md text-lg font-medium mb-2"
                >About</a
              >
            </nav>

            <div class="mt-6 space-y-3">
              <button class="w-full bg-orange-500 text-white py-3 rounded-lg font-semibold">
                Get Started
              </button>
              <button
                class="w-full border border-orange-500 text-orange-500 bg-transparent py-3 rounded-lg font-semibold"
              >
                Join AI Early Access
              </button>
            </div>
          </div>
        </div>

        <!-- Mobile Menu Overlay -->
        <div
          v-if="isMobileMenuOpen"
          @click="closeMobileMenu"
          class="fixed inset-0 bg-black/50 z-40"
        ></div>
      </nav>
    </header>

    <!-- Hero Section -->
    <section
  id="home"
  class="text-white pt-8 sm:pt-8 pb-16 md:pb-24 min-h-[85vh] md:min-h-[120vh] flex items-center pt-10 md:pt-0"
  style="background: linear-gradient(180deg, #42389E 0%, #0F1026 100%); clip-path: polygon(0 0, 100% 0, 100% 60%, 0 100%);"
>
      <div class="max-w-3xl mx-auto px-4 md:py-4 w-full text-center">
        <h1 class="text-[1.75rem] md:text-[3rem] font-normal font-weight-700 leading-tight tracking-tight mb-3">
          The First
          <span style="background-color: #F9A71E; padding: 0.25rem 0.5rem; border-radius: 0.25rem;"><span style="background-image: linear-gradient(135deg, #42389E, #0F1026); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; font-weight: 600;">Dart-Native</span></span>
          Feature Flag With DartCodeAI
        </h1>
<div class="text-center">
        <p class="text-[0.95rem] md:text-base text-gray-200 font-normal font-weight-700 leading-relaxed mb-2">
          Feature flags built for Dart, Ship faster, roll back safely, and scale with AI-powered delivery
        </p>
      </div>

        <p class="text-sm md:text-base text-orange-400 font-semibold mb-6">
          Starting at just $1/month
        </p>

        <div class="flex flex-col md:flex-row gap-3 md:gap-4 justify-center max-w-md mx-auto">
          <button
            class="bg-[#F9A71E] text-black font-semibold rounded-lg px-6 py-3 hover:bg-orange-500 transition"
          >
          <span style="background-image: linear-gradient(180deg, #42389E, #0F1026); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;">Get Access</span>
          </button>
          <button
            class="border border-[#F9A71E] text-[#F9A71E] font-semibold rounded-lg px-6 py-3 hover:border-orange-500 hover:text-orange-500 transition"
          >
            Join AI Early Access
          </button>
        </div>
      </div>
    </section>

    <!-- Video Section -->
    <section class="relative z-20">
  <div class="max-w-screen-lg mx-auto px-4">
    <div
      class="relative bg-gray-100 rounded-lg aspect-video flex items-center justify-center shadow-md overflow-hidden -mt-40 md:-mt-56"
    >
      <!-- Play Button -->
      <div class="bg-red-600 rounded-full p-5 cursor-pointer transition-transform active:scale-95 shadow-lg">
        <svg class="w-12 h-12 text-white" fill="currentColor" viewBox="0 0 24 24">
          <path d="M8 5v14l11-7z" />
        </svg>
      </div>
    </div>
  </div>
</section>

    <!-- Trusted By Section -->
    <section class="bg-white py-12 md:py-14">
      <div class="max-w-screen-xl mx-auto px-4">
        <p class="text-black-400 text-center mb-6 text-sm font-medium">
          Trusted by some amazing companies like
        </p>
        <div
          class="flex flex-wrap justify-center items-center gap-6 text-gray-400"
        >
        <div style="display: flex; align-items: center; justify-content: center; width: 120px; height: 40px; background: white; border-radius: 8px; padding: 8px; box-shadow: 0 2px 4px rgba(0,0,0,0.1);">
            <img src="/assets/images/logos/google.png" alt="Google" style="height: 60px; width: auto; object-fit: contain;">
          </div>
          <div style="display: flex; align-items: center; justify-content: center; width: 120px; height: 40px; background: white; border-radius: 8px; padding: 8px; box-shadow: 0 2px 4px rgba(0,0,0,0.1);">
            <img src="/assets/images/logos/amazon.png" alt="Amazon" style="height: 60px; width: auto; object-fit: contain;">
          </div>
          <div style="display: flex; align-items: center; justify-content: center; width: 120px; height: 40px; background: white; border-radius: 8px; padding: 8px; box-shadow: 0 2px 4px rgba(0,0,0,0.1);">
            <img src="/assets/images/logos/microsoft_azure.png" alt="Microsoft Azure" style="height: 60px; width: auto; object-fit: contain;">
          </div>
          <div style="display: flex; align-items: center; justify-content: center; width: 120px; height: 40px; background: white; border-radius: 8px; padding: 8px; box-shadow: 0 2px 4px rgba(0,0,0,0.1);">
            <img src="/assets/images/logos/digitalocean.png" alt="DigitalOcean" style="height: 60px; width: auto; object-fit: contain;">
          </div>
          <div style="display: flex; align-items: center; justify-content: center; width: 120px; height: 40px; background: white; border-radius: 8px; padding: 8px; box-shadow: 0 2px 4px rgba(0,0,0,0.1);">
            <img src="/assets/images/logos/ibm.png" alt="IBM" style="height: 60px; width: auto; object-fit: contain;">
          </div>
        </div>
      </div>
    </section>

    <!-- What Is IntelliToggle Section -->
    <section id="features" class="bg-white py-16 md:py-20">
      <div class="max-w-screen-xl mx-auto px-4">
        <h2 class="text-center text-purple-700 text-2xl font-semibold mb-8">
          <span style="background-image: linear-gradient(180deg, #42389E, #0F1026); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;">What Is IntelliToggle</span>
</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 md:gap-12 items-center">
          <div>
            <h3 class="text-black text-[1.75rem] md:text-3xl leading-snug mb-4">
              Your AI-Driven App's Control Panel For Feature Releases
            </h3>
            <p class="text-gray-500 text-sm md:text-base leading-relaxed mb-4">
              IntelliToggle is a “Dart-Powered” feature flag that lets you turn features on/off instantly in your application without redeploying code. It allows you control roll-outs, run experiments, and fix bugs faster.
            </p>
            <h3 class="text-black text-[1.75rem] md:text-3xl leading-snug mb-4">
              Benefits
            </h3>
            <ul class="text-gray-500 space-y-1">
              <li class="flex items-center"><span class="w-2 h-2 bg-black rounded-full mr-3"></span><span class="text-sm">Toggle new features without app updates</span></li>
              <li class="flex items-center"><span class="w-2 h-2 bg-black rounded-full mr-3"></span><span class="text-sm">Roll out to specific users or regions</span></li>
              <li class="flex items-center"><span class="w-2 h-2 bg-black rounded-full mr-3"></span><span class="text-sm">Instantly rollback when needed</span></li>
            </ul>
          </div>
          <div class="rounded-lg p-4 order-first md:order-none">
            <img src="/assets/images/logos/Frame1.png" alt="Frame1" style="height: auto; width: 830px;">
          </div>
        </div>
      </div>
    </section>

    <!-- OpenFeature Section -->
    <section class="bg-gray-100 py-16 md:py-20">
      <div class="max-w-screen-xl mx-auto px-4">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 md:gap-12 items-center">
            <div class="flex items-center mb-3">
              <img src="/assets/images/logos/Frame2.png" alt="Frame2" style="height: auto; width: 830px;">
            </div>
          <div>
            <h3 class="text-2xl md:text-3xl font-bold text-gray-900 ml-16 mb-3">
              Seamless Feature Management with OpenFeature
            </h3>
            <p class="text-gray-500 text-base md:text-lg ml-16 mb-6">
              Integrate with OpenFeature for a standardized approach to feature flag management across your entire stack.
            </p>
            <button class="bg-orange-500 text-white px-6 py-3 ml-16 rounded-lg font-semibold">
              Learn More
            </button>
          </div>
        </div>
      </div>
    </section>

    <!-- Control & Power Section -->
    <section class="bg-white py-16 md:py-20">
      <div class="max-w-screen-xl mx-auto px-4">
        <h2 class="text-center text-black text-2xl font-bold mb-12">
          Control & Power-focused
        </h2>

        <div class="grid gap-6 md:gap-8 grid-cols-1 md:grid-cols-2 lg:grid-cols-3">
          <div class="bg-white rounded-lg p-6">
              <img src="/assets/images/logos/Frame3.png" alt="Frame3" style="height: auto; width: 400px;">
            <h3 class="text-black text-lg font-semibold mb-1">Connect</h3>
            <p class="text-gray-400 mb-4">Install SDK in your Dart project in 2 mins.</p>
            <button class="text-orange-500 border border-orange-500 px-4 py-2 rounded text-sm font-semibold">
              View Documentation
            </button>
          </div>

          <div class="bg-white rounded-lg p-6">
              <img src="/assets/images/logos/Frame4.png" alt="Frame4" style="height: auto; width: 400px;">
            <h3 class="text-black text-lg font-semibold mb-1">Create Flags</h3>
            <p class="text-gray-400 mb-4">Define features in IntelliToggle dashboard.</p>
            <button class="text-orange-500 border border-orange-500 px-4 py-2 rounded text-sm font-semibold">
              View Documentation
            </button>
          </div>

          <div class="bg-white rounded-lg p-6">
              <img src="/assets/images/logos/Frame5.png" alt="Frame5" style="height: auto; width: 400px;">
            <h3 class="text-black text-lg font-semibold mb-1">Ship & Control</h3>
            <p class="text-gray-400 mb-4">Flip switches anytime, see instant results.</p>
            <button class="text-orange-500 border border-orange-500 px-4 py-2 rounded text-sm font-semibold">
              View Documentation
            </button>
          </div>
        </div>
      </div>
    </section>

    <!-- Comparison Table Section -->
    <section class="bg-grey-50 py-16 md:py-20">
      <div class="max-w-screen-xl mx-auto px-4">
        <div class="text-center mb-12">
          <h2 class="text-black text-3xl font-bold mb-2">Dart-Powered Feature Flag</h2>
          <p class="text-black text-xl mb-4">Not Another Generic Feature Flag Tool</p>
          <p class="text-gray-400 text-base">
            Most tools are built for every language, which means extra layers and slower toggles. IntelliToggle is built in Dart, for Dart — so it’s faster, safer, and built for your stack.
          </p>
        </div>

        <div class="overflow-hidden rounded-lg shadow">
          <table class="w-full border-collapse">
            <thead>
              <tr class=" text-white" style="background: linear-gradient(180deg, #42389E, #0F1026); backdrop-filter: blur(10px);">
                <th class="text-left text-white font-semibold px-6 py-4">Features</th>
                <th class="text-center text-white font-semibold px-6 py-4">IntelliToggle</th>
                <th class="text-center text-white font-semibold px-6 py-4">Other Feature Flag</th>
              </tr>
            </thead>
            <tbody>
              <tr class="bg-gray-300">
                <td class="px-6 py-3 text-gray-700">Dart-native SDK & server</td>
    <td class="px-6 py-3 text-center">✓</td>
    <td class="px-6 py-3 text-center">✗</td>
              </tr>
              <tr class="bg-gray-300">
    <td class="px-6 py-3 text-gray-700">End-to-end type safety</td>
    <td class="px-6 py-3 text-center">✓</td>
    <td class="px-6 py-3 text-center">✗</td>
  </tr>
  <tr class="bg-gray-300">
    <td class="px-6 py-3 text-gray-700">AI-assisted roll-outs & cleanup</td>
    <td class="px-6 py-3 text-center">✓</td>
    <td class="px-6 py-3 text-center">✗</td>
              </tr>
              <tr class="bg-gray-300">
                <td class="px-6 py-3 text-gray-700">A/B testing built-in</td>
    <td class="px-6 py-3 text-center">✓</td>
    <td class="px-6 py-3 text-center">✗</td>
              </tr>
              <tr class="bg-gray-300">
                <td class="px-6 py-3 text-gray-700">Dart-Powered SDKs</td>
    <td class="px-6 py-3 text-center">✓</td>
    <td class="px-6 py-3 text-center">✗</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </section>

    <!-- AI Features Section -->
    <section
  class="relative py-20 text-white"
  style="background: linear-gradient(203deg, #42389E, #1A1C3D); background-image: url('/background.jpg'); background-size: cover; background-position: center;">

  <div class="absolute inset-0 bg-gradient-to-br from-[#42389E]/80 to-[#1A1C3D]/80"></div>

      <!-- subtle grid -->
      <div class="relative z-10 max-w-6xl mx-auto px-6">
        <div class="text-center mb-12">
          <span
            class="inline-block bg-[#F9A71E] text-black font-semibold text-sm px-3 py-1 rounded-full mb-3"
            >
            <span style="background-image: linear-gradient(180deg, #42389E, #0F1026); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;">Coming Soon</span></span
          >
          <h2 class="text-white text-3xl md:text-4xl font-bold">
            DartCodeAI That Actually Changes Flagging
          </h2>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
          <div class="border border-white/20 rounded-lg text-center p-6 shadow-lg flex flex-col scale-80 justify-between h-full">
            <div class="rounded-md flex items-center justify-center mb-3">
            <img src="/flag-icon.svg" alt="AutoFlag Icon" class="w-6 h-6 text-white" />
          </div>
            <h3 class="text-white text-lg font-semibold mb-1">AutoFlag AI (LLM Assisted Flag Creation)</h3>
            <p class="text-gray-200 text-sm">Automatically generate feature flags using AI assistance</p>
          </div>

          <div class="bg-transparent border border-white/20 rounded-lg text-center p-6 shadow-lg scale-80 justify-between h-full">
            <div class="rounded-md flex items-center justify-center mb-3">
            <img src="/smart-ramp.svg" alt="AutoFlag Icon" class="w-6 h-6 text-white" />
          </div>
            <h3 class="text-white text-lg font-semibold mb-1">SmartRamp AI (AI Driven Rollout Optimization)</h3>
            <p class="text-gray-200 text-sm">Optimize feature rollouts with AI-driven insights</p>
          </div>

          <div class="bg-transparent border border-white/20 rounded-lg text-center p-6 shadow-lg scale-80 justify-between h-full">
            <div class="rounded-md flex items-center justify-center mb-3">
            <img src="/explain-flag.svg" alt="AutoFlag Icon" class="w-6 h-6 text-white" />
          </div>
            <h3 class="text-white text-lg font-semibold mb-1">ExplainFlags AI (LLM Root-Cause Insights)</h3>
            <p class="text-gray-200 text-sm">Get AI-powered insights into feature flag performance</p>
          </div>

          <div class="bg-transparent border border-white/20 rounded-lg text-center p-6 shadow-lg scale-80 justify-between h-full">
            <div class="rounded-md flex items-center justify-center mb-3">
            <img src="/Auto-segment.svg" alt="AutoFlag Icon" class="w-6 h-6 text-white" />
            </div>
            <h3 class="text-white text-lg font-semibold mb-1">AutoSegment AI (Behavioral Segmentation)</h3>
            <p class="text-gray-200 text-sm">Automatically segment users based on behavior patterns</p>
          </div>
        </div>

        <div class="mt-12 text-center max-w-8xl mx-auto">
    <span class="text-[#F9A71E] text-xl font-semibold whitespace-nowrap">
      Enterprise Only
    </span>
  <div class="border border-white/20 rounded-lg px-6 py-4 mt-6 flex flex-col md:flex-row items-center justify-between gap-4">

    <p class="text-white text-base flex-1 text-center md:text-left">
      <span class="text-[#F9A71E] font-semibold">Be The First</span> To Try Out Our New AI Features.
    </p>

    <div class="flex w-full md:w-auto gap-3">
      <input
        type="email"
        placeholder="Enter your email"
        class="flex-1 px-4 py-2 rounded-lg outline-none text-gray-900"
      />
      <button class="bg-[#F9A71E] text-black px-4 py-2 rounded text-sm font-medium">
        <span style="background-image: linear-gradient(180deg, #42389E, #0F1026); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;">Join AI Early Access</span>
      </button>
    </div>
  </div>
</div>
      </div>
    </section>

    <!-- Pricing Section -->
    <section id="pricing" class="bg-[#F7F7FC] py-16 md:py-20">
  <div class="max-w-screen-md mx-auto px-4">
    <h2 class="text-center text-3xl font-bold text-gray-900 mb-12">
      Plans Built For Every Stage Of Growth
    </h2>

    <!-- Price Box -->
    <div class="text-center mb-10">
  <!-- Gradient price box -->
  <div class="inline-block bg-gradient-to-r from-[#42389E] to-[#1A1C3D] text-white px-10 py-6 rounded-lg mb-4">
    <p class="text-sm mb-1">Prices starts at</p>
    <h3 class="text-5xl font-bold">
      $10 <span class="text-lg font-normal">/month</span>
    </h3>
  </div>

  <!-- Yellow button below -->
   <div>
  <button class="bg-[#F9A71E] text-black px-8 py-3 rounded-md font-semibold">
    <span style="background-image: linear-gradient(180deg, #42389E, #0F1026); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;">View Subscription Details</span>
  </button>
</div>
</div>

    <!-- Free Plan Box -->
    <div class="flex flex-col sm:flex-row gap-24 max-w-8xl bg-white rounded-lg shadow-md p-6 text-left">
      <div>
      <h3 class="text-lg font-bold text-gray-900 mb-2">Start Your 7-Day Free Sandbox Plan</h3>
      <p class="text-gray-600 mb-6">
        Join over 1,000+ startups already growing with Untitled.
      </p>
      </div>
      <div class="flex flex-col items-center sm:flex-row justify-center gap-3">
        <div>
        <button class="bg-[#F9A71E] text-white px-3 py-1.5 w-full sm:w-auto rounded text-xs font-medium">
          <span style="background-image: linear-gradient(180deg, #42389E, #0F1026); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;">Get Started</span>
</button>
</div>
<div>
<button class="border border-orange-500 text-orange-500 px-3 py-1.5 rounded text-xs font-medium">
  Learn More
</button>
</div>
      </div>
    </div>
  </div>
</section>


    <!-- Why Teams Use IntelliToggle Section -->
    <section id="about" class="bg-white py-16 px-4">
      <div class="max-w-screen-xl mx-auto px-16">
        <h2 class="text-center text-3xl font-bold text-gray-900 mb-12">Why Teams Use IntelliToggle</h2>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-12">
          <div class="text-left">
            <img src="/two-way.png" alt="Frame6" style="height: auto; width: 75px;"></img>
            <h3 class="text-lg font-semibold text-gray-900 mt-6 mb-1">Safer, faster rollouts</h3>
            <p class="text-gray-600 text-sm">Control feature releases in minutes, not weeks without risking production stability.</p>
          </div>

          <div class="text-left">
            <img src="/parachute.png" alt="Frame6" style="height: auto; width: 75px;"></img>
            <h3 class="text-lg font-semibold text-gray-900 mt-6 mb-1">Confidence to ship</h3>
            <p class="text-gray-600 text-sm">“Flip, target, and roll back. Engineers ship more often knowing they can undo mistakes.</p>
          </div>

          <div class="text-left">
            <img src="/ai.png" alt="Frame6" style="height: auto; width: 75px;"></img>
            <h3 class="text-lg font-semibold text-gray-900 mt-6 mb-1">Future-ready with AI delivery</h3>
            <p class="text-gray-600 text-sm">Built for Dart workflows and already prepared for AI-powered rollout automation tomorrow.</p>
          </div>
        </div>

        <!-- Case Study Banner -->
        <div class="bg-gray-300 flex flex-col md:flex-row items-center justify-between py-4 px-4 md:px-6 rounded-lg text-left text-black gap-3 md:gap-0">
          <p class="text-sm md:text-lg text-center md:text-left">
            <span class="font-bold">Read a 2-min case note:</span> How a sample Flutter app shipped faster with IntelliToggle
          </p>
          <button class="bg-[#F9A71E] text-black px-6 py-3 rounded-lg font-semibold w-full md:w-auto">
            <span style="background-image: linear-gradient(180deg, #42389E, #0F1026); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;">Read Now</span>
          </button>
        </div>
      </div>
    </section>

    <!-- Final CTA Section -->
    <section class="py-16 md:py-20 flex justify-center items-center bg-white">
  <div
    class="relative w-full max-w-5xl mx-auto rounded-lg shadow-lg px-6 py-12 text-center"
    style="
      background: linear-gradient(135deg, #42389E, #0F1026);
      box-shadow: 0 0 10px rgba(0,0,0,0.15);
    "
  >
    <!-- Subtle grid overlay -->
    <div
      class="absolute inset-0 bg-[url('/background-pattern.png')] opacity-20 rounded-lg"
    ></div>

    <!-- Content -->
    <div class="relative z-10">
      <h2 class="text-white text-2xl md:text-3xl font-bold mb-4">
        Launch Features Confidently With AI Driven Feature Flags
      </h2>
      <p class="text-gray-200 text-sm md:text-base mb-6">
        Start for free, scale as your team grows
      </p>
      <div class="flex flex-col md:flex-row gap-4 justify-center">
        <button
          class="bg-[#F9A71E] text-black px-6 py-3 rounded-md font-semibold hover:bg-orange-500 transition"
        >
          <span style="background-image: linear-gradient(180deg, #42389E, #0F1026); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;">Start for $1/mo</span>
        </button>
        <button
          class="border border-[#F9A71E] text-[#F9A71E] px-6 py-3 rounded-md font-semibold hover:border-orange-500 hover:text-orange-500 transition"
        >
          Join AI Early Access
        </button>
      </div>
    </div>
  </div>
</section>


    <!-- Footer -->
    <footer class="bg-gray-100 py-14">
      <div class="max-w-screen-xl mx-auto px-4">
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <!-- Logo and Description -->
          <div>
            <div class="flex items-center mb-3">
              <img src="/logo-blue.png" alt="IntelliToggle" class="w-15 h-10"></img>
            </div>
            <p class="text-gray-600">
              IntelliToggle is built by AORTEM, a company focused on powering scalable, multi-platform developer tools.
            </p>
          </div>

          <!-- Links -->
          <div class="grid grid-cols-2 gap-8">
            <div>
              <h4 class="text-lg font-semibold text-gray-900 mb-3">Resources</h4>
              <ul class="space-y-2 text-gray-600">
                <li><a href="#" class="hover:text-gray-900">Why IntelliToggle is different</a></li>
                <li><a href="#" class="hover:text-gray-900">Customer Support</a></li>
                <li><a href="#" class="hover:text-gray-900">Terms & Conditions</a></li>
                <li><a href="#" class="hover:text-gray-900">Privacy Policy</a></li>
              </ul>
            </div>
            <div>
              <h4 class="text-lg font-semibold text-gray-900 mb-3">Company</h4>
              <ul class="space-y-2 text-gray-600">
                <li><a href="#" class="hover:text-gray-900">Pricing</a></li>
                <li><a href="#" class="hover:text-gray-900">Documentation</a></li>
                <li><a href="#" class="hover:text-gray-900">About Us</a></li>
              </ul>
            </div>
          </div>

          <!-- Newsletter -->
          <div>
            <h4 class="text-lg font-semibold text-gray-900 mb-3">Subscribe to our newsletter</h4>
            <div style="display: flex; width: 100%; max-width: 400px; border-radius: 0.5rem; overflow: hidden; border: 1px solid #d1d5db;">
  <input 
    type="email" 
    placeholder="Enter email address" 
    style="flex: 1; padding: 0.75rem; border: none; outline: none; font-size: 0.9rem;"
  >
  <button 
    style="background: #f9a71e; color: #1A1C3D; padding: 0.75rem 1.25rem; font-weight: 600; border: none; cursor: pointer; font-size: 0.9rem;"
  >
  <span style="background-image: linear-gradient(180deg, #42389E, #0F1026); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;">Subscribe</span>
  </button>
</div>
          </div>
        </div>

        <div class="border-t border-gray-300 mt-10 pt-6 text-center text-gray-500">
          <p>&copy; 2024 IntelliToggle. All rights reserved.</p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount, watch } from 'vue'

const isMobileMenuOpen = ref(false)
const scrolled = ref(false)

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
}

const closeMobileMenu = () => {
  isMobileMenuOpen.value = false
}

// Body scroll lock when menu open
const lockScroll = () => document.body.classList.add('overflow-hidden')
const unlockScroll = () => document.body.classList.remove('overflow-hidden')

onMounted(() => {
  const stop = watch(isMobileMenuOpen, v => (v ? lockScroll() : unlockScroll()))
  
  const handleScroll = () => {
    scrolled.value = window.scrollY > 50
  }
  
  window.addEventListener('scroll', handleScroll)
  
  onBeforeUnmount(() => {
    window.removeEventListener('scroll', handleScroll)
    unlockScroll()
  })
})
</script>

<style scoped>
/* Ensure system font fallback similar to the original */
:host, .font-sans {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
}
</style>
