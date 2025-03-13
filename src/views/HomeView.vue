<template>
  <div class="min-h-screen flex flex-col bg-slate-50 text-gray-800">
    <!-- Header -->
    <header class="bg-teal-600 text-white shadow-md sticky top-0 z-50">
      <div class="container mx-auto py-4 px-6 flex justify-between items-center">
        <div class="flex items-center gap-2">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-6 w-6"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.747 0 3.332.477 4.5 1.253v13C19.832 18.477 18.247 18 16.5 18c-1.746 0-3.332.477-4.5 1.253"
            />
          </svg>
          <h1 class="text-xl font-bold">GasBelajar</h1>
        </div>
        <div class="hidden md:flex items-center gap-6">
          <router-link
            v-for="item in navItems"
            :key="item.path"
            :to="item.path"
            class="hover:text-teal-200 transition-colors"
          >
            {{ item.name }}
          </router-link>
        </div>
        <button class="md:hidden text-xl" @click="toggleMobileMenu">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-6 w-6"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            />
          </svg>
        </button>
      </div>
      <!-- Mobile menu -->
      <div v-if="isMobileMenuOpen" class="md:hidden container mx-auto px-6 py-4 bg-teal-700">
        <div class="flex flex-col space-y-3">
          <router-link
            v-for="item in navItems"
            :key="item.path"
            :to="item.path"
            class="hover:text-teal-200 transition-colors"
            @click="closeMobileMenu"
          >
            {{ item.name }}
          </router-link>
        </div>
      </div>
    </header>

    <!-- Hero Section -->
    <section class="bg-gradient-to-br from-teal-600 to-emerald-700 text-white py-16 md:py-24">
      <div class="container mx-auto px-6 flex flex-col items-center text-center">
        <h2 class="text-3xl md:text-5xl font-bold mb-6">Dokumentasi HTML & Network</h2>
        <p class="text-lg md:text-xl max-w-2xl mb-10">
          Pelajari HTML dan konsep jaringan dengan dokumentasi interaktif.
        </p>
        <div class="flex flex-col md:flex-row gap-4">
          <button
            @click="scrollToDocSection"
            class="bg-white text-teal-700 px-6 py-3 rounded-lg font-semibold hover:bg-gray-100 transition-colors"
          >
            Mulai Belajar
          </button>
        </div>
      </div>
    </section>

    <!-- Main Content -->
    <main class="flex-grow">
      <!-- Documentation Categories -->
      <section id="doc-section" ref="docSection" class="py-16 container mx-auto px-6">
        <h3 class="text-2xl md:text-3xl font-bold text-center mb-12">Pilih Kategori Dokumentasi</h3>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
          <!-- HTML Documentation -->
          <div
            class="bg-white rounded-xl shadow-lg overflow-hidden hover:shadow-xl transition-shadow"
          >
            <div
              class="h-40 bg-gradient-to-r from-amber-400 to-orange-500 flex items-center justify-center"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-16 w-16 text-white"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"
                />
              </svg>
            </div>
            <div class="p-6">
              <h4 class="text-xl font-bold mb-3">Dokumentasi HTML</h4>
              <p class="text-gray-600 mb-4">
                Pelajari struktur dasar web dengan dokumentasi lengkap tentang elemen HTML, atribut,
                dan best practices.
              </p>
              <div class="space-y-2">
                <div
                  v-for="(feature, index) in htmlFeatures"
                  :key="index"
                  class="flex items-center gap-2 text-gray-700"
                >
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-5 w-5 text-green-500"
                    viewBox="0 0 20 20"
                    fill="currentColor"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                      clip-rule="evenodd"
                    />
                  </svg>
                  <span>{{ feature }}</span>
                </div>
              </div>
              <router-link
                to="/html-docs"
                class="mt-6 inline-block bg-amber-500 text-white px-4 py-2 rounded-lg hover:bg-amber-600 transition-colors"
              >
                Lihat Dokumentasi HTML
              </router-link>
            </div>
          </div>

          <!-- Network Documentation -->
          <div
            class="bg-white rounded-xl shadow-lg overflow-hidden hover:shadow-xl transition-shadow"
          >
            <div
              class="h-40 bg-gradient-to-r from-sky-400 to-blue-500 flex items-center justify-center"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-16 w-16 text-white"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M5 12h14M5 12a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v4a2 2 0 01-2 2M5 12a2 2 0 00-2 2v4a2 2 0 002 2h14a2 2 0 002-2v-4a2 2 0 00-2-2m-2-4h.01M17 16h.01"
                />
              </svg>
            </div>
            <div class="p-6">
              <h4 class="text-xl font-bold mb-3">Dokumentasi Network</h4>
              <p class="text-gray-600 mb-4">
                Pelajari konsep jaringan untuk web development, termasuk HTTP, APIs, dan komunikasi
                client-server.
              </p>
              <div class="space-y-2">
                <div
                  v-for="(feature, index) in networkFeatures"
                  :key="index"
                  class="flex items-center gap-2 text-gray-700"
                >
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-5 w-5 text-green-500"
                    viewBox="0 0 20 20"
                    fill="currentColor"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                      clip-rule="evenodd"
                    />
                  </svg>
                  <span>{{ feature }}</span>
                </div>
              </div>
              <router-link
                to="/network-docs"
                class="mt-6 inline-block bg-blue-500 text-white px-4 py-2 rounded-lg hover:bg-blue-600 transition-colors"
              >
                Lihat Dokumentasi Network
              </router-link>
            </div>
          </div>
        </div>
      </section>

      <!-- Features -->
      <section class="py-16 bg-slate-100">
        <div class="container mx-auto px-6">
          <h3 class="text-2xl md:text-3xl font-bold text-center mb-12">Fitur Dokumentasi</h3>

          <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
            <div
              v-for="(feature, index) in docFeatures"
              :key="index"
              class="bg-white p-6 rounded-lg shadow-md"
            >
              <div class="w-14 h-14 bg-teal-100 rounded-full flex items-center justify-center mb-4">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-6 w-6 text-teal-600"
                  :viewBox="feature.viewBox"
                  fill="none"
                  stroke="currentColor"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    :d="feature.path"
                  />
                </svg>
              </div>
              <h4 class="text-lg font-semibold mb-2">{{ feature.title }}</h4>
              <p class="text-gray-600">{{ feature.description }}</p>
            </div>
          </div>
        </div>
      </section>

      <!-- Start Learning -->
      <section class="py-16 container mx-auto px-6">
        <div
          class="bg-gradient-to-r from-emerald-600 to-teal-600 rounded-xl p-8 md:p-12 text-white text-center"
        >
          <h3 class="text-2xl md:text-3xl font-bold mb-4">Siap untuk mulai belajar?</h3>
          <p class="text-lg max-w-2xl mx-auto mb-8">
            Akses dokumentasi HTML dan Network sekarang untuk meningkatkan kemampuan pengembangan
            web Anda.
          </p>
          <button
            @click="scrollToDocSection"
            class="bg-white text-teal-700 px-6 py-3 rounded-lg font-semibold hover:bg-gray-100 transition-colors"
          >
            Masuk ke Dokumentasi
          </button>
        </div>
      </section>
    </main>

    <!-- Footer -->
    <footer class="bg-slate-800 text-white py-10">
      <div class="container mx-auto px-6">
        <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
          <div>
            <h5 class="font-bold text-lg mb-4">GasBelajar</h5>
            <p class="text-gray-400">Dokumentasi komprehensif untuk pengembangan web modern.</p>
          </div>

          <div>
            <h5 class="font-bold text-lg mb-4">Dokumentasi</h5>
            <ul class="space-y-2">
              <li v-for="(item, index) in docLinks" :key="index">
                <router-link
                  :to="item.path"
                  class="text-gray-400 hover:text-white transition-colors"
                >
                  {{ item.name }}
                </router-link>
              </li>
            </ul>
          </div>

          <div>
            <h5 class="font-bold text-lg mb-4">Tentang</h5>
            <ul class="space-y-2">
              <li v-for="(item, index) in aboutLinks" :key="index">
                <router-link
                  :to="item.path"
                  class="text-gray-400 hover:text-white transition-colors"
                >
                  {{ item.name }}
                </router-link>
              </li>
            </ul>
          </div>

          <div>
            <h5 class="font-bold text-lg mb-4">Tim Pengembang</h5>
            <div class="flex gap-4"></div>
            <ul class="space-y-2 text-gray-400">
              <li>Rio Rapansyah</li>
              <li>Fauzul Azmi Siregar</li>
            </ul>
          </div>
        </div>

        <div class="border-t border-gray-700 mt-8 pt-8 text-center text-gray-400">
          <p>&copy; {{ currentYear }} Tim Web GasBelajar</p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
import { ref, computed } from 'vue'

export default {
  name: 'DocumentationOverview',
  setup() {
    const isMobileMenuOpen = ref(false)
    const docSection = ref(null)

    const toggleMobileMenu = () => {
      isMobileMenuOpen.value = !isMobileMenuOpen.value
    }

    const closeMobileMenu = () => {
      isMobileMenuOpen.value = false
    }

    const scrollToDocSection = () => {
      docSection.value.scrollIntoView({ behavior: 'smooth' })
    }

    const currentYear = computed(() => new Date().getFullYear())

    const navItems = [
      { name: 'Beranda', path: '/' },
      { name: 'HTML', path: '/html-docs' },
      { name: 'Network', path: '/network-docs' },
    ]

    const htmlFeatures = [
      'Dasar-dasar HTML5',
      'Struktur dokumen',
      'Form dan validasi',
      'Semantic HTML',
    ]

    const networkFeatures = [
      'Protokol HTTP/HTTPS',
      'REST API',
      'Websockets',
      'Performance dan caching',
    ]

    const docFeatures = [
      {
        title: 'Konten Komprehensif',
        description:
          'Dokumentasi lengkap dengan contoh kode, best practices, dan penjelasan detail.',
        viewBox: '0 0 24 24',
        path: 'M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.747 0 3.332.477 4.5 1.253v13C19.832 18.477 18.247 18 16.5 18c-1.746 0-3.332.477-4.5 1.253',
      },
      {
        title: 'Interaktif',
        description: 'Editor kode dan preview langsung untuk mencoba konsep yang dipelajari.',
        viewBox: '0 0 24 24',
        path: 'M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4',
      },
      {
        title: 'Responsif',
        description: 'Diakses dengan nyaman dari perangkat desktop, tablet, maupun mobile.',
        viewBox: '0 0 24 24',
        path: 'M12 18h.01M8 21h8a2 2 0 002-2V5a2 2 0 00-2-2H8a2 2 0 00-2 2v14a2 2 0 002 2z',
      },
    ]

    const docLinks = [
      { name: 'HTML', path: '/html-docs' },
      { name: 'Network', path: '/network-docs' },
      { name: 'API', path: '/api' },
      { name: 'Tutorial', path: '/tutorial' },
    ]

    const aboutLinks = [
      { name: 'Tim', path: '/team' },
      { name: 'Kontak', path: '/contact' },
      { name: 'Blog', path: '/blog' },
      { name: 'Kebijakan Privasi', path: '/privacy' },
    ]

    const socialLinks = [
      {
        url: 'https://github.com',
        path: 'M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z',
      },
      {
        url: 'https://twitter.com',
        path: 'M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z',
      },
      {
        url: 'https://linkedin.com',
        path: 'M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z',
      },
      {
        url: 'https://youtube.com',
        path: 'M23.498 6.186a3.016 3.016 0 0 0-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 0 0 .502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 0 0 2.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 0 0 2.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z',
      },
    ]

    return {
      isMobileMenuOpen,
      docSection,
      toggleMobileMenu,
      closeMobileMenu,
      scrollToDocSection,
      currentYear,
      navItems,
      htmlFeatures,
      networkFeatures,
      docFeatures,
      docLinks,
      aboutLinks,
      socialLinks,
    }
  },
}
</script>
