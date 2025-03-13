<template>
  <div class="min-h-screen bg-gradient-to-br from-purple-50 to-violet-100">
    <!-- Header -->
    <header class="py-6 px-4 bg-white shadow-md sticky top-0 z-50">
      <div class="max-w-[1050px] px-4 w-full mx-auto flex items-center justify-between">
        <h1
          @click="navigateToHome"
          class="text-2xl font-bold text-purple-600 cursor-pointer hover:text-purple-700 transition duration-300"
        >
          Network<span class="text-orange-500">Docs</span>
        </h1>
        <nav class="flex items-center">
          <button
            @click="navigateToHome"
            class="mr-6 text-gray-600 hover:text-purple-600 flex items-center transition duration-300"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5 mr-1"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6"
              />
            </svg>
            Home
          </button>
          <ul class="flex space-x-6">
            <li v-for="item in menuItems" :key="item.id">
              <a
                @click="scrollToSection(item.target)"
                class="text-gray-600 hover:text-purple-600 cursor-pointer transition duration-300"
              >
                {{ item.name }}
              </a>
            </li>
          </ul>
        </nav>
      </div>
    </header>

    <!-- Hero Section -->
    <section class="py-20 px-4">
      <div class="container mx-auto text-center">
        <h1 class="text-5xl font-bold text-gray-800 mb-6">
          Jaringan & <span class="text-purple-600">Web Hosting</span> Dasar
        </h1>
        <p class="text-xl text-gray-600 max-w-2xl mx-auto mb-10">
          Panduan informatif tentang konsep jaringan komputer dan web hosting untuk memahami
          infrastruktur internet modern.
        </p>
        <div class="flex justify-center space-x-4">
          <button
            @click="scrollToContent"
            class="bg-purple-600 hover:bg-purple-700 text-white px-8 py-3 rounded-lg shadow-lg transition transform hover:scale-105 duration-300 flex items-center"
          >
            Lihat Dokumentasi
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5 ml-2"
              viewBox="0 0 20 20"
              fill="currentColor"
            >
              <path
                fill-rule="evenodd"
                d="M16.707 10.293a1 1 0 010 1.414l-6 6a1 1 0 01-1.414 0l-6-6a1 1 0 111.414-1.414L9 14.586V3a1 1 0 012 0v11.586l4.293-4.293a1 1 0 011.414 0z"
                clip-rule="evenodd"
              />
            </svg>
          </button>
          <button
            @click="navigateToHome"
            class="bg-white border border-purple-600 text-purple-600 hover:bg-purple-50 px-8 py-3 rounded-lg shadow-lg transition duration-300 flex items-center"
          >
            Kembali ke Home
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5 ml-2"
              viewBox="0 0 20 20"
              fill="currentColor"
            >
              <path
                fill-rule="evenodd"
                d="M9.707 16.707a1 1 0 01-1.414 0l-6-6a1 1 0 010-1.414l6-6a1 1 0 011.414 1.414L5.414 9H17a1 1 0 110 2H5.414l4.293 4.293a1 1 0 010 1.414z"
                clip-rule="evenodd"
              />
            </svg>
          </button>
        </div>
      </div>
    </section>

    <!-- Main Content -->
    <main class="py-16 px-4" id="content">
      <div class="container mx-auto max-w-5xl bg-white rounded-xl shadow-xl p-8">
        <!-- Toggle Theme Button -->
        <div class="flex justify-end mb-6">
          <button
            @click="toggleTheme"
            class="p-2 rounded-full bg-gray-100 hover:bg-gray-200 transition duration-300"
          >
            <svg
              v-if="darkMode"
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6 text-yellow-500"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 11-8 0 4 4 0 018 0z"
              />
            </svg>
            <svg
              v-else
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6 text-gray-700"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z"
              />
            </svg>
          </button>
        </div>

        <!-- Introduction -->
        <div class="mb-16 border-b pb-8">
          <div class="flex items-center mb-6">
            <div class="w-12 h-12 bg-purple-100 rounded-full flex items-center justify-center mr-4">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-6 w-6 text-purple-600"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"
                />
              </svg>
            </div>
            <h2 class="text-3xl font-bold text-gray-800">Tentang Dokumentasi</h2>
          </div>
          <p class="text-gray-600 text-lg">
            Dokumentasi ini menjelaskan konsep dasar jaringan komputer seperti LAN, WAN, dan MAN,
            serta konsep web hosting seperti domain dan hosting. Setiap bagian memiliki penjelasan
            yang informatif dan contoh untuk membantu pemahaman. Dokumentasi ini cocok untuk pemula
            yang ingin memahami infrastruktur internet dan web.
          </p>
        </div>

        <!-- Network Concepts Section -->
        <div class="space-y-16">
          <!-- LAN -->
          <section
            id="lan"
            :class="{ 'bg-gray-900 text-white': darkMode, 'bg-white': !darkMode }"
            class="transition duration-500 rounded-lg p-6 shadow-lg transform hover:scale-[1.01]"
          >
            <h3
              class="text-2xl font-bold mb-4"
              :class="{ 'text-purple-300': darkMode, 'text-purple-600': !darkMode }"
            >
              LAN (Local Area Network)
            </h3>
            <p class="mb-6" :class="{ 'text-gray-300': darkMode, 'text-gray-600': !darkMode }">
              LAN adalah jaringan komputer yang mencakup area geografis yang terbatas seperti rumah,
              kantor, atau gedung. LAN biasanya dikelola oleh satu organisasi dan menggunakan
              teknologi seperti Ethernet atau Wi-Fi.
            </p>
            <div
              class="bg-gray-100 p-4 rounded-lg"
              :class="{ 'bg-gray-800': darkMode, 'bg-gray-100': !darkMode }"
            >
              <div class="flex flex-col md:flex-row items-center">
                <div class="md:w-1/3 mb-4 md:mb-0 md:mr-6">
                  <div class="bg-purple-100 p-4 rounded-lg">
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      class="h-24 w-24 mx-auto text-purple-600"
                      fill="none"
                      viewBox="0 0 24 24"
                      stroke="currentColor"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M9 3v2m6-2v2M9 19v2m6-2v2M5 9H3m2 6H3m18-6h-2m2 6h-2M7 19h10a2 2 0 002-2V7a2 2 0 00-2-2H7a2 2 0 00-2 2v10a2 2 0 002 2zM9 9h6v6H9V9z"
                      />
                    </svg>
                  </div>
                </div>
                <div class="md:w-2/3">
                  <h4
                    class="text-lg font-semibold mb-2"
                    :class="{ 'text-white': darkMode, 'text-gray-800': !darkMode }"
                  >
                    Karakteristik LAN:
                  </h4>
                  <ul
                    class="list-disc pl-5 space-y-2"
                    :class="{ 'text-gray-300': darkMode, 'text-gray-700': !darkMode }"
                  >
                    <li>Mencakup area geografis yang kecil (satu gedung atau kampus)</li>
                    <li>Kecepatan transfer data tinggi (10 Mbps hingga 10 Gbps)</li>
                    <li>Dikelola secara pribadi oleh individu atau organisasi</li>
                    <li>Contoh: Jaringan kantor, jaringan rumah, jaringan laboratorium komputer</li>
                    <li>Teknologi: Ethernet, Wi-Fi (802.11), Token Ring</li>
                  </ul>
                </div>
              </div>
            </div>
            <div class="mt-4">
              <button
                @click="showCode('lan')"
                class="text-sm px-4 py-2 rounded-lg border"
                :class="{
                  'border-gray-600 text-gray-300 hover:bg-gray-700': darkMode,
                  'border-purple-300 text-purple-600 hover:bg-purple-50': !darkMode,
                }"
              >
                {{ codeVisible.lan ? 'Sembunyikan Diagram' : 'Lihat Diagram' }}
              </button>
              <div
                v-if="codeVisible.lan"
                class="mt-4 p-4 rounded-lg"
                :class="{
                  'bg-gray-800 text-gray-300': darkMode,
                  'bg-gray-100 text-gray-800': !darkMode,
                }"
              >
                <div class="flex justify-center">
                  <div class="relative w-full max-w-md h-64 border border-gray-300 rounded-lg p-4">
                    <!-- Router -->
                    <div
                      class="absolute top-4 left-1/2 transform -translate-x-1/2 bg-purple-100 p-2 rounded-lg border border-purple-300 text-center"
                    >
                      <div class="text-purple-600 font-bold">Router/Switch</div>
                    </div>

                    <!-- Devices -->
                    <div
                      class="absolute top-24 left-1/4 transform -translate-x-1/2 bg-gray-100 p-2 rounded-lg border border-gray-300 text-center"
                    >
                      <div class="text-gray-600">Komputer 1</div>
                    </div>

                    <div
                      class="absolute top-24 left-1/2 transform -translate-x-1/2 bg-gray-100 p-2 rounded-lg border border-gray-300 text-center"
                    >
                      <div class="text-gray-600">Komputer 2</div>
                    </div>

                    <div
                      class="absolute top-24 left-3/4 transform -translate-x-1/2 bg-gray-100 p-2 rounded-lg border border-gray-300 text-center"
                    >
                      <div class="text-gray-600">Printer</div>
                    </div>

                    <!-- Lines -->
                    <div
                      class="absolute top-14 left-1/2 transform -translate-x-1/2 w-0.5 h-10 bg-purple-400"
                    ></div>
                    <div
                      class="absolute top-14 left-1/4 transform -translate-x-1/2 w-0.5 h-10 bg-purple-400"
                    ></div>
                    <div
                      class="absolute top-14 left-3/4 transform -translate-x-1/2 w-0.5 h-10 bg-purple-400"
                    ></div>

                    <div
                      class="absolute top-14 left-1/2 transform -translate-x-1/2 w-1/2 h-0.5 bg-purple-400"
                    ></div>

                    <div
                      class="absolute bottom-4 left-1/2 transform -translate-x-1/2 text-center w-full"
                    >
                      <div class="text-sm text-gray-500 italic">Contoh Topologi LAN Sederhana</div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </section>

          <!-- MAN -->
          <section
            id="man"
            :class="{ 'bg-gray-900 text-white': darkMode, 'bg-white': !darkMode }"
            class="transition duration-500 rounded-lg p-6 shadow-lg transform hover:scale-[1.01]"
          >
            <h3
              class="text-2xl font-bold mb-4"
              :class="{ 'text-purple-300': darkMode, 'text-purple-600': !darkMode }"
            >
              MAN (Metropolitan Area Network)
            </h3>
            <p class="mb-6" :class="{ 'text-gray-300': darkMode, 'text-gray-600': !darkMode }">
              MAN adalah jaringan komputer yang mencakup area geografis yang lebih besar dari LAN
              tetapi lebih kecil dari WAN, biasanya mencakup satu kota atau area metropolitan. MAN
              sering digunakan untuk menghubungkan beberapa LAN dalam satu kota.
            </p>
            <div
              class="bg-gray-100 p-4 rounded-lg"
              :class="{ 'bg-gray-800': darkMode, 'bg-gray-100': !darkMode }"
            >
              <div class="flex flex-col md:flex-row items-center">
                <div class="md:w-1/3 mb-4 md:mb-0 md:mr-6">
                  <div class="bg-purple-100 p-4 rounded-lg">
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      class="h-24 w-24 mx-auto text-purple-600"
                      fill="none"
                      viewBox="0 0 24 24"
                      stroke="currentColor"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M19 21V5a2 2 0 00-2-2H7a2 2 0 00-2 2v16m14 0h2m-2 0h-5m-9 0H3m2 0h5M9 7h1m-1 4h1m4-4h1m-1 4h1m-5 10v-5a1 1 0 011-1h2a1 1 0 011 1v5m-4 0h4"
                      />
                    </svg>
                  </div>
                </div>
                <div class="md:w-2/3">
                  <h4
                    class="text-lg font-semibold mb-2"
                    :class="{ 'text-white': darkMode, 'text-gray-800': !darkMode }"
                  >
                    Karakteristik MAN:
                  </h4>
                  <ul
                    class="list-disc pl-5 space-y-2"
                    :class="{ 'text-gray-300': darkMode, 'text-gray-700': !darkMode }"
                  >
                    <li>
                      Mencakup area geografis yang lebih besar (satu kota atau area metropolitan)
                    </li>
                    <li>Kecepatan transfer data menengah (biasanya 100 Mbps hingga 1 Gbps)</li>
                    <li>Biasanya dikelola oleh beberapa organisasi atau penyedia layanan</li>
                    <li>
                      Contoh: Jaringan kampus universitas, jaringan pemerintah kota, jaringan antar
                      cabang bank
                    </li>
                    <li>Teknologi: DQDB (Distributed Queue Dual Bus), ATM, FDDI, Metro Ethernet</li>
                  </ul>
                </div>
              </div>
            </div>
            <div class="mt-4">
              <button
                @click="showCode('man')"
                class="text-sm px-4 py-2 rounded-lg border"
                :class="{
                  'border-gray-600 text-gray-300 hover:bg-gray-700': darkMode,
                  'border-purple-300 text-purple-600 hover:bg-purple-50': !darkMode,
                }"
              >
                {{ codeVisible.man ? 'Sembunyikan Diagram' : 'Lihat Diagram' }}
              </button>
              <div
                v-if="codeVisible.man"
                class="mt-4 p-4 rounded-lg"
                :class="{
                  'bg-gray-800 text-gray-300': darkMode,
                  'bg-gray-100 text-gray-800': !darkMode,
                }"
              >
                <div class="flex justify-center">
                  <div class="relative w-full max-w-md h-64 border border-gray-300 rounded-lg p-4">
                    <!-- Central MAN -->
                    <div
                      class="absolute top-4 left-1/2 transform -translate-x-1/2 bg-purple-100 p-2 rounded-lg border border-purple-300 text-center"
                    >
                      <div class="text-purple-600 font-bold">Backbone MAN</div>
                    </div>

                    <!-- Buildings -->
                    <div
                      class="absolute top-24 left-1/4 transform -translate-x-1/2 bg-gray-100 p-2 rounded-lg border border-gray-300 text-center"
                    >
                      <div class="text-gray-600">Gedung A</div>
                      <div class="text-xs text-gray-500">(LAN)</div>
                    </div>

                    <div
                      class="absolute top-24 left-1/2 transform -translate-x-1/2 bg-gray-100 p-2 rounded-lg border border-gray-300 text-center"
                    >
                      <div class="text-gray-600">Gedung B</div>
                      <div class="text-xs text-gray-500">(LAN)</div>
                    </div>

                    <div
                      class="absolute top-24 left-3/4 transform -translate-x-1/2 bg-gray-100 p-2 rounded-lg border border-gray-300 text-center"
                    >
                      <div class="text-gray-600">Gedung C</div>
                      <div class="text-xs text-gray-500">(LAN)</div>
                    </div>

                    <!-- Lines -->
                    <div
                      class="absolute top-14 left-1/2 transform -translate-x-1/2 w-0.5 h-10 bg-purple-400"
                    ></div>
                    <div
                      class="absolute top-14 left-1/4 transform -translate-x-1/2 w-0.5 h-10 bg-purple-400"
                    ></div>
                    <div
                      class="absolute top-14 left-3/4 transform -translate-x-1/2 w-0.5 h-10 bg-purple-400"
                    ></div>

                    <div
                      class="absolute top-14 left-1/2 transform -translate-x-1/2 w-1/2 h-0.5 bg-purple-400"
                    ></div>

                    <div
                      class="absolute bottom-4 left-1/2 transform -translate-x-1/2 text-center w-full"
                    >
                      <div class="text-sm text-gray-500 italic">Contoh Topologi MAN Sederhana</div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </section>

          <!-- WAN -->
          <section
            id="wan"
            :class="{ 'bg-gray-900 text-white': darkMode, 'bg-white': !darkMode }"
            class="transition duration-500 rounded-lg p-6 shadow-lg transform hover:scale-[1.01]"
          >
            <h3
              class="text-2xl font-bold mb-4"
              :class="{ 'text-purple-300': darkMode, 'text-purple-600': !darkMode }"
            >
              WAN (Wide Area Network)
            </h3>
            <p class="mb-6" :class="{ 'text-gray-300': darkMode, 'text-gray-600': !darkMode }">
              WAN adalah jaringan komputer yang mencakup area geografis yang luas, seperti negara
              atau benua. Internet adalah contoh terbesar dari WAN. WAN menghubungkan beberapa LAN
              dan MAN yang terpisah secara geografis.
            </p>
            <div
              class="bg-gray-100 p-4 rounded-lg"
              :class="{ 'bg-gray-800': darkMode, 'bg-gray-100': !darkMode }"
            >
              <div class="flex flex-col md:flex-row items-center">
                <div class="md:w-1/3 mb-4 md:mb-0 md:mr-6">
                  <div class="bg-purple-100 p-4 rounded-lg">
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      class="h-24 w-24 mx-auto text-purple-600"
                      fill="none"
                      viewBox="0 0 24 24"
                      stroke="currentColor"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M3.055 11H5a2 2 0 012 2v1a2 2 0 002 2 2 2 0 012 2v2.945M8 3.935V5.5A2.5 2.5 0 0010.5 8h.5a2 2 0 012 2 2 2 0 104 0 2 2 0 012-2h1.064M15 20.488V18a2 2 0 012-2h3.064M21 12a9 9 0 11-18 0 9 9 0 0118 0z"
                      />
                    </svg>
                  </div>
                </div>
                <div class="md:w-2/3">
                  <h4
                    class="text-lg font-semibold mb-2"
                    :class="{ 'text-white': darkMode, 'text-gray-800': !darkMode }"
                  >
                    Karakteristik WAN:
                  </h4>
                  <ul
                    class="list-disc pl-5 space-y-2"
                    :class="{ 'text-gray-300': darkMode, 'text-gray-700': !darkMode }"
                  >
                    <li>Mencakup area geografis yang sangat luas (negara, benua, atau global)</li>
                    <li>Kecepatan transfer data bervariasi (dari beberapa Kbps hingga Gbps)</li>
                    <li>Dikelola oleh beberapa organisasi atau penyedia layanan internet (ISP)</li>
                    <li>
                      Contoh: Internet, jaringan perusahaan multinasional, jaringan perbankan global
                    </li>
                    <li>Teknologi: MPLS, Frame Relay, ATM, Leased Line, Satellite, Fiber Optic</li>
                  </ul>
                </div>
              </div>
            </div>
            <div class="mt-4">
              <button
                @click="showCode('wan')"
                class="text-sm px-4 py-2 rounded-lg border"
                :class="{
                  'border-gray-600 text-gray-300 hover:bg-gray-700': darkMode,
                  'border-purple-300 text-purple-600 hover:bg-purple-50': !darkMode,
                }"
              >
                {{ codeVisible.wan ? 'Sembunyikan Diagram' : 'Lihat Diagram' }}
              </button>
              <div
                v-if="codeVisible.wan"
                class="mt-4 p-4 rounded-lg"
                :class="{
                  'bg-gray-800 text-gray-300': darkMode,
                  'bg-gray-100 text-gray-800': !darkMode,
                }"
              >
                <div class="flex justify-center">
                  <div class="relative w-full max-w-md h-80 border border-gray-300 rounded-lg p-4">
                    <!-- Internet Cloud -->
                    <div
                      class="absolute top-4 left-1/2 transform -translate-x-1/2 bg-purple-100 p-2 rounded-lg border border-purple-300 text-center w-32"
                    >
                      <div class="text-purple-600 font-bold">Internet</div>
                    </div>

                    <!-- Cities -->
                    <div
                      class="absolute top-24 left-1/4 transform -translate-x-1/2 bg-gray-100 p-2 rounded-lg border border-gray-300 text-center"
                    >
                      <div class="text-gray-600">Jakarta</div>
                      <div class="text-xs text-gray-500">(MAN)</div>
                    </div>

                    <div
                      class="absolute top-24 left-3/4 transform -translate-x-1/2 bg-gray-100 p-2 rounded-lg border border-gray-300 text-center"
                    >
                      <div class="text-gray-600">Surabaya</div>
                      <div class="text-xs text-gray-500">(MAN)</div>
                    </div>

                    <div
                      class="absolute top-48 left-1/2 transform -translate-x-1/2 bg-gray-100 p-2 rounded-lg border border-gray-300 text-center"
                    >
                      <div class="text-gray-600">Bandung</div>
                      <div class="text-xs text-gray-500">(MAN)</div>
                    </div>

                    <!-- Lines -->
                    <div
                      class="absolute top-14 left-1/2 transform -translate-x-1/2 w-0.5 h-10 bg-purple-400"
                    ></div>
                    <div
                      class="absolute top-14 left-1/4 transform -translate-x-1/2 rotate-45 w-0.5 h-14 bg-purple-400 origin-top"
                    ></div>
                    <div
                      class="absolute top-14 left-3/4 transform -translate-x-1/2 -rotate-45 w-0.5 h-14 bg-purple-400 origin-top"
                    ></div>
                    <div
                      class="absolute top-24 left-1/2 transform -translate-x-1/2 w-0.5 h-24 bg-purple-400"
                    ></div>

                    <div
                      class="absolute bottom-4 left-1/2 transform -translate-x-1/2 text-center w-full"
                    >
                      <div class="text-sm text-gray-500 italic">Contoh Topologi WAN Sederhana</div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </section>

          <!-- Domain -->
          <section
            id="domain"
            :class="{ 'bg-gray-900 text-white': darkMode, 'bg-white': !darkMode }"
            class="transition duration-500 rounded-lg p-6 shadow-lg transform hover:scale-[1.01]"
          >
            <h3
              class="text-2xl font-bold mb-4"
              :class="{ 'text-purple-300': darkMode, 'text-purple-600': !darkMode }"
            >
              Domain
            </h3>
            <p class="mb-6" :class="{ 'text-gray-300': darkMode, 'text-gray-600': !darkMode }">
              Domain adalah nama unik yang mengidentifikasi situs web di internet. Domain berfungsi
              sebagai alamat yang mudah diingat untuk mengakses server web, menggantikan alamat IP
              numerik yang sulit diingat.
            </p>
            <div
              class="bg-gray-100 p-4 rounded-lg"
              :class="{ 'bg-gray-800': darkMode, 'bg-gray-100': !darkMode }"
            >
              <div class="flex flex-col md:flex-row items-center">
                <div class="md:w-1/3 mb-4 md:mb-0 md:mr-6">
                  <div class="bg-purple-100 p-4 rounded-lg">
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      class="h-24 w-24 mx-auto text-purple-600"
                      fill="none"
                      viewBox="0 0 24 24"
                      stroke="currentColor"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M21 12a9 9 0 01-9 9m9-9a9 9 0 00-9-9m9 9H3m9 9a9 9 0 01-9-9m9 9c1.657 0 3-4.03 3-9s-1.343-9-3-9m0 18c-1.657 0-3-4.03-3-9s1.343-9 3-9m-9 9a9 9 0 019-9"
                      />
                    </svg>
                  </div>
                </div>
                <div class="md:w-2/3">
                  <h4
                    class="text-lg font-semibold mb-2"
                    :class="{ 'text-white': darkMode, 'text-gray-800': !darkMode }"
                  >
                    Struktur Domain:
                  </h4>
                  <ul
                    class="list-disc pl-5 space-y-2"
                    :class="{ 'text-gray-300': darkMode, 'text-gray-700': !darkMode }"
                  >
                    <li>
                      <strong>Top-Level Domain (TLD)</strong>: Bagian terakhir dari domain (.com,
                      .org, .net, .id)
                    </li>
                    <li>
                      <strong>Second-Level Domain (SLD)</strong>: Nama utama domain (google,
                      facebook, microsoft)
                    </li>
                    <li>
                      <strong>Subdomain</strong>: Bagian opsional sebelum nama domain utama
                      (mail.google.com, drive.google.com)
                    </li>
                  </ul>
                </div>
              </div>

              <div class="mt-6">
                <h4
                  class="text-lg font-semibold mb-2"
                  :class="{ 'text-white': darkMode, 'text-gray-800': !darkMode }"
                >
                  Contoh Domain dan Penjelasannya:
                </h4>
                <div class="overflow-x-auto">
                  <table class="min-w-full border-collapse">
                    <thead>
                      <tr>
                        <th
                          class="border p-2"
                          :class="{
                            'border-gray-600 bg-gray-700': darkMode,
                            'border-gray-300 bg-gray-200': !darkMode,
                          }"
                        >
                          Domain
                        </th>
                        <th
                          class="border p-2"
                          :class="{
                            'border-gray-600 bg-gray-700': darkMode,
                            'border-gray-300 bg-gray-200': !darkMode,
                          }"
                        >
                          Jenis TLD
                        </th>
                        <th
                          class="border p-2"
                          :class="{
                            'border-gray-600 bg-gray-700': darkMode,
                            'border-gray-300 bg-gray-200': !darkMode,
                          }"
                        >
                          Penjelasan
                        </th>
                      </tr>
                    </thead>
                    <tbody>
                      <tr :class="{ 'bg-gray-800': darkMode, 'bg-white': !darkMode }">
                        <td
                          class="border p-2"
                          :class="{ 'border-gray-600': darkMode, 'border-gray-300': !darkMode }"
                        >
                          google.com
                        </td>
                        <td
                          class="border p-2"
                          :class="{ 'border-gray-600': darkMode, 'border-gray-300': !darkMode }"
                        >
                          .com (komersial)
                        </td>
                        <td
                          class="border p-2"
                          :class="{ 'border-gray-600': darkMode, 'border-gray-300': !darkMode }"
                        >
                          Domain untuk mesin pencari Google, menggunakan TLD komersial yang paling
                          umum digunakan
                        </td>
                      </tr>
                      <tr :class="{ 'bg-gray-800': darkMode, 'bg-white': !darkMode }">
                        <td
                          class="border p-2"
                          :class="{ 'border-gray-600': darkMode, 'border-gray-300': !darkMode }"
                        >
                          kemendikbud.go.id
                        </td>
                        <td
                          class="border p-2"
                          :class="{ 'border-gray-600': darkMode, 'border-gray-300': !darkMode }"
                        >
                          .go.id (pemerintah Indonesia)
                        </td>
                        <td
                          class="border p-2"
                          :class="{ 'border-gray-600': darkMode, 'border-gray-300': !darkMode }"
                        >
                          Domain untuk Kementerian Pendidikan dan Kebudayaan Indonesia, menggunakan
                          TLD khusus untuk lembaga pemerintah Indonesia
                        </td>
                      </tr>
                      <tr :class="{ 'bg-gray-800': darkMode, 'bg-white': !darkMode }">
                        <td
                          class="border p-2"
                          :class="{ 'border-gray-600': darkMode, 'border-gray-300': !darkMode }"
                        >
                          ui.ac.id
                        </td>
                        <td
                          class="border p-2"
                          :class="{ 'border-gray-600': darkMode, 'border-gray-300': !darkMode }"
                        >
                          .ac.id (akademik Indonesia)
                        </td>
                        <td
                          class="border p-2"
                          :class="{ 'border-gray-600': darkMode, 'border-gray-300': !darkMode }"
                        >
                          Domain untuk Universitas Indonesia, menggunakan TLD khusus untuk institusi
                          akademik di Indonesia
                        </td>
                      </tr>
                      <tr :class="{ 'bg-gray-800': darkMode, 'bg-white': !darkMode }">
                        <td
                          class="border p-2"
                          :class="{ 'border-gray-600': darkMode, 'border-gray-300': !darkMode }"
                        >
                          wikipedia.org
                        </td>
                        <td
                          class="border p-2"
                          :class="{ 'border-gray-600': darkMode, 'border-gray-300': !darkMode }"
                        >
                          .org (organisasi)
                        </td>
                        <td
                          class="border p-2"
                          :class="{ 'border-gray-600': darkMode, 'border-gray-300': !darkMode }"
                        >
                          Domain untuk Wikipedia, menggunakan TLD untuk organisasi non-profit
                        </td>
                      </tr>
                      <tr :class="{ 'bg-gray-800': darkMode, 'bg-white': !darkMode }">
                        <td
                          class="border p-2"
                          :class="{ 'border-gray-600': darkMode, 'border-gray-300': !darkMode }"
                        >
                          mail.google.com
                        </td>
                        <td
                          class="border p-2"
                          :class="{ 'border-gray-600': darkMode, 'border-gray-300': !darkMode }"
                        >
                          .com dengan subdomain
                        </td>
                        <td
                          class="border p-2"
                          :class="{ 'border-gray-600': darkMode, 'border-gray-300': !darkMode }"
                        >
                          Subdomain "mail" dari google.com, digunakan untuk layanan Gmail
                        </td>
                      </tr>
                    </tbody>
                  </table>
                </div>
              </div>
            </div>
            <div class="mt-4">
              <button
                @click="showCode('domain')"
                class="text-sm px-4 py-2 rounded-lg border"
                :class="{
                  'border-gray-600 text-gray-300 hover:bg-gray-700': darkMode,
                  'border-purple-300 text-purple-600 hover:bg-purple-50': !darkMode,
                }"
              >
                {{ codeVisible.domain ? 'Sembunyikan Diagram' : 'Lihat Diagram' }}
              </button>
              <div
                v-if="codeVisible.domain"
                class="mt-4 p-4 rounded-lg"
                :class="{
                  'bg-gray-800 text-gray-300': darkMode,
                  'bg-gray-100 text-gray-800': !darkMode,
                }"
              >
                <div class="flex justify-center">
                  <div class="w-full max-w-md">
                    <div class="text-center mb-4 font-semibold">
                      Struktur Domain: mail.example.com
                    </div>
                    <div class="flex items-center justify-center space-x-2 mb-6">
                      <div
                        class="bg-purple-100 p-2 rounded border border-purple-300 text-purple-700"
                      >
                        mail
                      </div>
                      <div class="text-gray-500">.</div>
                      <div
                        class="bg-orange-100 p-2 rounded border border-orange-300 text-orange-700"
                      >
                        example
                      </div>
                      <div class="text-gray-500">.</div>
                      <div
                        class="bg-violet-100 p-2 rounded border border-violet-300 text-violet-700"
                      >
                        com
                      </div>
                    </div>
                    <div class="flex items-center justify-center space-x-2">
                      <div class="text-center">
                        <div class="text-xs text-gray-500 mb-1">Subdomain</div>
                        <div class="w-16 h-0.5 bg-purple-400"></div>
                      </div>
                      <div class="text-center">
                        <div class="text-xs text-gray-500 mb-1">Second-Level Domain</div>
                        <div class="w-24 h-0.5 bg-orange-400"></div>
                      </div>
                      <div class="text-center">
                        <div class="text-xs text-gray-500 mb-1">Top-Level Domain</div>
                        <div class="w-16 h-0.5 bg-violet-400"></div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </section>

          <!-- Hosting -->
          <section
            id="hosting"
            :class="{ 'bg-gray-900 text-white': darkMode, 'bg-white': !darkMode }"
            class="transition duration-500 rounded-lg p-6 shadow-lg transform hover:scale-[1.01]"
          >
            <h3
              class="text-2xl font-bold mb-4"
              :class="{ 'text-purple-300': darkMode, 'text-purple-600': !darkMode }"
            >
              Hosting
            </h3>
            <p class="mb-6" :class="{ 'text-gray-300': darkMode, 'text-gray-600': !darkMode }">
              Hosting adalah layanan yang memungkinkan individu dan organisasi untuk menyimpan
              konten website, aplikasi, atau data lainnya di server yang terhubung ke internet.
              Server hosting menyimpan semua file website dan membuatnya tersedia untuk diakses
              melalui domain.
            </p>
            <div
              class="bg-gray-100 p-4 rounded-lg"
              :class="{ 'bg-gray-800': darkMode, 'bg-gray-100': !darkMode }"
            >
              <div class="flex flex-col md:flex-row items-center">
                <div class="md:w-1/3 mb-4 md:mb-0 md:mr-6">
                  <div class="bg-purple-100 p-4 rounded-lg">
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      class="h-24 w-24 mx-auto text-purple-600"
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
                </div>
                <div class="md:w-2/3">
                  <h4
                    class="text-lg font-semibold mb-2"
                    :class="{ 'text-white': darkMode, 'text-gray-800': !darkMode }"
                  >
                    Jenis-jenis Hosting:
                  </h4>
                  <ul
                    class="list-disc pl-5 space-y-2"
                    :class="{ 'text-gray-300': darkMode, 'text-gray-700': !darkMode }"
                  >
                    <li>
                      <strong>Shared Hosting</strong>: Beberapa website berbagi satu server. Paling
                      ekonomis tetapi sumber daya terbatas.
                    </li>
                    <li>
                      <strong>VPS (Virtual Private Server)</strong>: Server fisik dibagi menjadi
                      beberapa server virtual. Lebih banyak sumber daya dan kontrol.
                    </li>
                    <li>
                      <strong>Dedicated Hosting</strong>: Satu server fisik khusus untuk satu
                      website. Performa maksimal dan kontrol penuh.
                    </li>
                    <li>
                      <strong>Cloud Hosting</strong>: Hosting yang menggunakan jaringan server
                      terdistribusi. Skalabel dan handal.
                    </li>
                    <li>
                      <strong>Managed WordPress Hosting</strong>: Hosting khusus dioptimalkan untuk
                      WordPress.
                    </li>
                  </ul>
                </div>
              </div>

              <div class="mt-6">
                <h4
                  class="text-lg font-semibold mb-2"
                  :class="{ 'text-white': darkMode, 'text-gray-800': !darkMode }"
                >
                  Hubungan Domain dan Hosting:
                </h4>
                <p class="mb-4" :class="{ 'text-gray-300': darkMode, 'text-gray-700': !darkMode }">
                  Domain dan hosting adalah dua komponen berbeda yang bekerja bersama untuk membuat
                  website dapat diakses di internet:
                </p>
                <ul
                  class="list-disc pl-5 space-y-2"
                  :class="{ 'text-gray-300': darkMode, 'text-gray-700': !darkMode }"
                >
                  <li><strong>Domain</strong> adalah alamat website (seperti example.com)</li>
                  <li><strong>Hosting</strong> adalah tempat penyimpanan file website</li>
                  <li>DNS (Domain Name System) menghubungkan domain ke alamat IP server hosting</li>
                  <li>
                    Ketika seseorang mengakses domain, browser mereka diarahkan ke server hosting
                    yang menyimpan file website
                  </li>
                </ul>
              </div>
            </div>
            <div class="mt-4">
              <button
                @click="showCode('hosting')"
                class="text-sm px-4 py-2 rounded-lg border"
                :class="{
                  'border-gray-600 text-gray-300 hover:bg-gray-700': darkMode,
                  'border-purple-300 text-purple-600 hover:bg-purple-50': !darkMode,
                }"
              >
                {{ codeVisible.hosting ? 'Sembunyikan Diagram' : 'Lihat Diagram' }}
              </button>
              <div
                v-if="codeVisible.hosting"
                class="mt-4 p-4 rounded-lg"
                :class="{
                  'bg-gray-800 text-gray-300': darkMode,
                  'bg-gray-100 text-gray-800': !darkMode,
                }"
              >
                <div class="flex justify-center">
                  <div class="relative w-full max-w-md h-80 border border-gray-300 rounded-lg p-4">
                    <!-- User -->
                    <div
                      class="absolute top-4 left-1/6 transform -translate-x-1/2 bg-gray-100 p-2 rounded-lg border border-gray-300 text-center"
                    >
                      <div class="text-gray-600">Pengguna</div>
                      <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="h-8 w-8 mx-auto text-gray-600"
                        fill="none"
                        viewBox="0 0 24 24"
                        stroke="currentColor"
                      >
                        <path
                          stroke-linecap="round"
                          stroke-linejoin="round"
                          stroke-width="2"
                          d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z"
                        />
                      </svg>
                    </div>

                    <!-- DNS -->
                    <div
                      class="absolute top-4 left-1/2 transform -translate-x-1/2 bg-orange-100 p-2 rounded-lg border border-orange-300 text-center"
                    >
                      <div class="text-orange-700">DNS Server</div>
                      <div class="text-xs text-orange-600">example.com → 192.168.1.1</div>
                    </div>

                    <!-- Web Server -->
                    <div
                      class="absolute top-4 left-5/6 transform -translate-x-1/2 bg-purple-100 p-2 rounded-lg border border-purple-300 text-center"
                    >
                      <div class="text-purple-700">Web Hosting</div>
                      <div class="text-xs text-purple-600">192.168.1.1</div>
                      <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="h-8 w-8 mx-auto text-purple-600"
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

                    <!-- Flow arrows -->
                    <div
                      class="absolute top-16 left-1/4 transform -translate-x-1/2 w-16 h-0.5 bg-gray-400"
                    ></div>
                    <div
                      class="absolute top-16 left-1/4 transform -translate-x-1/2 rotate-45 w-3 h-0.5 bg-gray-400 origin-right"
                    ></div>
                    <div
                      class="absolute top-14 left-1/4 transform -translate-x-1/2 -rotate-45 w-3 h-0.5 bg-gray-400 origin-right"
                    ></div>

                    <div
                      class="absolute top-16 left-2/3 transform -translate-x-1/2 w-16 h-0.5 bg-gray-400"
                    ></div>
                    <div
                      class="absolute top-16 left-2/3 transform -translate-x-1/2 rotate-45 w-3 h-0.5 bg-gray-400 origin-right"
                    ></div>
                    <div
                      class="absolute top-14 left-2/3 transform -translate-x-1/2 -rotate-45 w-3 h-0.5 bg-gray-400 origin-right"
                    ></div>

                    <!-- Steps -->
                    <div
                      class="absolute top-24 left-1/6 transform -translate-x-1/2 text-center w-32"
                    >
                      <div class="text-xs text-gray-500">1. Pengguna mengetik example.com</div>
                    </div>

                    <div
                      class="absolute top-24 left-1/2 transform -translate-x-1/2 text-center w-32"
                    >
                      <div class="text-xs text-gray-500">2. DNS menerjemahkan domain ke IP</div>
                    </div>

                    <div
                      class="absolute top-24 left-5/6 transform -translate-x-1/2 text-center w-32"
                    >
                      <div class="text-xs text-gray-500">
                        3. Server hosting mengirim konten website
                      </div>
                    </div>

                    <!-- Website content -->
                    <div
                      class="absolute top-40 left-1/2 transform -translate-x-1/2 bg-white p-2 rounded-lg border border-gray-300 text-center w-64"
                    >
                      <div class="text-gray-800 font-bold">Website</div>
                      <div class="flex justify-center space-x-2 mt-2">
                        <div class="bg-gray-200 w-12 h-2 rounded"></div>
                        <div class="bg-gray-200 w-12 h-2 rounded"></div>
                      </div>
                      <div class="flex justify-center space-x-2 mt-2">
                        <div class="bg-gray-200 w-8 h-8 rounded"></div>
                        <div class="bg-gray-200 w-8 h-8 rounded"></div>
                        <div class="bg-gray-200 w-8 h-8 rounded"></div>
                      </div>
                      <div class="bg-gray-200 w-full h-2 rounded mt-2"></div>
                    </div>

                    <!-- Return arrow -->
                    <div
                      class="absolute top-32 left-1/2 transform -translate-x-1/2 w-0.5 h-8 bg-gray-400"
                    ></div>
                    <div
                      class="absolute top-32 left-1/2 transform -translate-x-1/2 rotate-45 w-3 h-0.5 bg-gray-400 origin-left"
                    ></div>
                    <div
                      class="absolute top-32 left-1/2 transform -translate-x-1/2 -rotate-45 w-3 h-0.5 bg-gray-400 origin-left"
                    ></div>

                    <div
                      class="absolute bottom-4 left-1/2 transform -translate-x-1/2 text-center w-full"
                    >
                      <div class="text-sm text-gray-500 italic">Cara Kerja Domain dan Hosting</div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </section>
        </div>
      </div>
    </main>

    <!-- Footer -->
    <footer class="bg-gray-800 text-white py-12 px-4 mt-16">
      <div class="container mx-auto">
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div>
            <h4 class="text-xl font-bold mb-4">Network<span class="text-orange-500">Docs</span></h4>
            <p class="text-gray-400">
              Dokumentasi ini dibuat untuk tujuan pendidikan sebagai bagian dari tugas kuliah
              jaringan komputer dan infrastruktur web.
            </p>
          </div>
          <div>
            <h4 class="text-xl font-bold mb-4">Navigasi</h4>
            <ul class="space-y-2 text-gray-400">
              <li v-for="item in menuItems" :key="item.id">
                <a
                  @click="scrollToSection(item.target)"
                  class="hover:text-white cursor-pointer transition duration-300"
                >
                  {{ item.name }}
                </a>
              </li>
            </ul>
          </div>
          <div>
            <h4 class="text-xl font-bold mb-4">Tim Pengembang</h4>
            <ul class="space-y-2 text-gray-400">
              <li>Rio Rapansyah</li>
              <li>Fauzul Azmi Siregar</li>
            </ul>
          </div>
        </div>
        <div class="border-t border-gray-700 mt-8 pt-8 text-center text-gray-400">
          <p>
            &copy; {{ new Date().getFullYear() }} Network Documentation. Dari Tim Web GasBelajar
          </p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

// Menu items
const menuItems = [
  { id: 1, name: 'LAN', target: 'lan' },
  { id: 2, name: 'MAN', target: 'man' },
  { id: 3, name: 'WAN', target: 'wan' },
  { id: 4, name: 'Domain', target: 'domain' },
  { id: 5, name: 'Hosting', target: 'hosting' },
]

// Dark mode state
const darkMode = ref(false)

// Code visibility state
const codeVisible = ref({
  lan: false,
  man: false,
  wan: false,
  domain: false,
  hosting: false,
})

// Toggle dark mode
const toggleTheme = () => {
  darkMode.value = !darkMode.value
}

// Show/hide code
const showCode = (section) => {
  codeVisible.value[section] = !codeVisible.value[section]
}

// Scroll to section
const scrollToSection = (id) => {
  const element = document.getElementById(id)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth', block: 'start' })
  }
}

// Scroll to content
const scrollToContent = () => {
  const element = document.getElementById('content')
  if (element) {
    element.scrollIntoView({ behavior: 'smooth', block: 'start' })
  }
}

// Navigate to home page
const navigateToHome = () => {
  // You can replace this with your actual home page URL
  window.location.href = '/'
}

// Initialize
onMounted(() => {
  // Check system preference for dark mode
  if (window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches) {
    darkMode.value = true
  }
})
</script>
