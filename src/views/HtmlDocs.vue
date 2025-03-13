<template>
  <div class="min-h-screen bg-gradient-to-br from-blue-50 to-indigo-100">
    <!-- Header -->
    <header class="py-6 px-4 bg-white shadow-md sticky top-0 z-50">
      <div class="max-w-[1050px] px-4 w-full mx-auto flex items-center justify-between">
        <h1
          @click="navigateToHome"
          class="text-2xl font-bold text-indigo-600 cursor-pointer hover:text-indigo-700 transition duration-300"
        >
          HTML<span class="text-orange-500">Docs</span>
        </h1>
        <nav class="flex items-center">
          <button
            @click="navigateToHome"
            class="mr-6 text-gray-600 hover:text-indigo-600 flex items-center transition duration-300"
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
                class="text-gray-600 hover:text-indigo-600 cursor-pointer transition duration-300"
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
          Dokumentasi <span class="text-indigo-600">HTML</span> Praktikum
        </h1>
        <p class="text-xl text-gray-600 max-w-2xl mx-auto mb-10">
          Koleksi elemen HTML dasar yang informatif dan interaktif untuk menunjukkan hasil praktikum
          pemrograman web.
        </p>
        <div class="flex justify-center space-x-4">
          <button
            @click="scrollToContent"
            class="bg-indigo-600 hover:bg-indigo-700 text-white px-8 py-3 rounded-lg shadow-lg transition transform hover:scale-105 duration-300 flex items-center"
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
            class="bg-white border border-indigo-600 text-indigo-600 hover:bg-indigo-50 px-8 py-3 rounded-lg shadow-lg transition duration-300 flex items-center"
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
            <div class="w-12 h-12 bg-indigo-100 rounded-full flex items-center justify-center mr-4">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-6 w-6 text-indigo-600"
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
            Dokumentasi ini menunjukkan hasil praktikum pemrograman web saya, khususnya penggunaan
            elemen-elemen HTML dasar seperti heading, paragraph, line break (br), horizontal rule
            (hr), subscript (sub), superscript (sup), dan blockquote. Setiap bagian memiliki contoh
            dan penjelasan singkat tentang penggunaan dan tujuan masing-masing elemen.
          </p>
        </div>

        <!-- HTML Elements Section -->
        <div class="space-y-16">
          <!-- Headings -->
          <section
            id="headings"
            :class="{ 'bg-gray-900 text-white': darkMode, 'bg-white': !darkMode }"
            class="transition duration-500 rounded-lg p-6 shadow-lg transform hover:scale-[1.01]"
          >
            <h3
              class="text-2xl font-bold mb-4"
              :class="{ 'text-indigo-300': darkMode, 'text-indigo-600': !darkMode }"
            >
              Headings
            </h3>
            <p class="mb-6" :class="{ 'text-gray-300': darkMode, 'text-gray-600': !darkMode }">
              HTML menyediakan elemen heading dari h1 hingga h6, digunakan untuk menunjukkan tingkat
              kepentingan dan struktur konten.
            </p>
            <div
              class="bg-gray-100 p-4 rounded-lg"
              :class="{ 'bg-gray-800': darkMode, 'bg-gray-100': !darkMode }"
            >
              <h1
                class="text-4xl font-bold mb-2"
                :class="{ 'text-white': darkMode, 'text-gray-800': !darkMode }"
              >
                Heading 1
              </h1>
              <h2
                class="text-3xl font-bold mb-2"
                :class="{ 'text-white': darkMode, 'text-gray-800': !darkMode }"
              >
                Heading 2
              </h2>
              <h3
                class="text-2xl font-bold mb-2"
                :class="{ 'text-white': darkMode, 'text-gray-800': !darkMode }"
              >
                Heading 3
              </h3>
              <h4
                class="text-xl font-bold mb-2"
                :class="{ 'text-white': darkMode, 'text-gray-800': !darkMode }"
              >
                Heading 4
              </h4>
              <h5
                class="text-lg font-bold mb-2"
                :class="{ 'text-white': darkMode, 'text-gray-800': !darkMode }"
              >
                Heading 5
              </h5>
              <h6
                class="text-base font-bold"
                :class="{ 'text-white': darkMode, 'text-gray-800': !darkMode }"
              >
                Heading 6
              </h6>
            </div>
            <div class="mt-4">
              <button
                @click="showCode('headings')"
                class="text-sm px-4 py-2 rounded-lg border"
                :class="{
                  'border-gray-600 text-gray-300 hover:bg-gray-700': darkMode,
                  'border-indigo-300 text-indigo-600 hover:bg-indigo-50': !darkMode,
                }"
              >
                {{ codeVisible.headings ? 'Sembunyikan Kode' : 'Lihat Kode' }}
              </button>
              <pre
                v-if="codeVisible.headings"
                class="mt-4 p-4 rounded-lg text-sm overflow-auto"
                :class="{
                  'bg-gray-800 text-gray-300': darkMode,
                  'bg-gray-100 text-gray-800': !darkMode,
                }"
              >
    &lt;h1&gt;Heading 1&lt;/h1&gt;
    &lt;h2&gt;Heading 2&lt;/h2&gt;
    &lt;h3&gt;Heading 3&lt;/h3&gt;
    &lt;h4&gt;Heading 4&lt;/h4&gt;
    &lt;h5&gt;Heading 5&lt;/h5&gt;
    &lt;h6&gt;Heading 6&lt;/h6&gt;
                  </pre
              >
            </div>
          </section>

          <!-- Paragraphs -->
          <section
            id="paragraphs"
            :class="{ 'bg-gray-900 text-white': darkMode, 'bg-white': !darkMode }"
            class="transition duration-500 rounded-lg p-6 shadow-lg transform hover:scale-[1.01]"
          >
            <h3
              class="text-2xl font-bold mb-4"
              :class="{ 'text-indigo-300': darkMode, 'text-indigo-600': !darkMode }"
            >
              Paragraphs
            </h3>
            <p class="mb-6" :class="{ 'text-gray-300': darkMode, 'text-gray-600': !darkMode }">
              Elemen paragraph (&lt;p&gt;) digunakan untuk mengelompokkan teks ke dalam paragraf.
              Browser secara otomatis menambahkan ruang sebelum dan sesudah paragraf.
            </p>
            <div
              class="bg-gray-100 p-4 rounded-lg"
              :class="{ 'bg-gray-800': darkMode, 'bg-gray-100': !darkMode }"
            >
              <p class="mb-4" :class="{ 'text-white': darkMode, 'text-gray-800': !darkMode }">
                Ini adalah contoh paragraf pertama. Paragraf adalah blok teks yang terdiri dari satu
                atau lebih kalimat yang membahas topik atau ide tertentu. Paragraf digunakan untuk
                mengorganisir konten dan membuat teks lebih mudah dibaca.
              </p>
              <p :class="{ 'text-white': darkMode, 'text-gray-800': !darkMode }">
                Ini adalah contoh paragraf kedua. Perhatikan bahwa browser secara otomatis
                menambahkan margin antara paragraf. Hal ini membantu membedakan paragraf dan
                meningkatkan keterbacaan dokumen.
              </p>
            </div>
            <div class="mt-4">
              <button
                @click="showCode('paragraphs')"
                class="text-sm px-4 py-2 rounded-lg border"
                :class="{
                  'border-gray-600 text-gray-300 hover:bg-gray-700': darkMode,
                  'border-indigo-300 text-indigo-600 hover:bg-indigo-50': !darkMode,
                }"
              >
                {{ codeVisible.paragraphs ? 'Sembunyikan Kode' : 'Lihat Kode' }}
              </button>
              <pre
                v-if="codeVisible.paragraphs"
                class="mt-4 p-4 rounded-lg text-sm overflow-auto"
                :class="{
                  'bg-gray-800 text-gray-300': darkMode,
                  'bg-gray-100 text-gray-800': !darkMode,
                }"
              >
    &lt;p&gt;
      Ini adalah contoh paragraf pertama. Paragraf adalah blok teks yang terdiri dari satu atau lebih kalimat
      yang membahas topik atau ide tertentu. Paragraf digunakan untuk mengorganisir konten dan membuat teks lebih mudah dibaca.
    &lt;/p&gt;
    &lt;p&gt;
      Ini adalah contoh paragraf kedua. Perhatikan bahwa browser secara otomatis menambahkan margin antara paragraf.
      Hal ini membantu membedakan paragraf dan meningkatkan keterbacaan dokumen.
    &lt;/p&gt;
                  </pre
              >
            </div>
          </section>

          <!-- Line Breaks -->
          <section
            id="line-breaks"
            :class="{ 'bg-gray-900 text-white': darkMode, 'bg-white': !darkMode }"
            class="transition duration-500 rounded-lg p-6 shadow-lg transform hover:scale-[1.01]"
          >
            <h3
              class="text-2xl font-bold mb-4"
              :class="{ 'text-indigo-300': darkMode, 'text-indigo-600': !darkMode }"
            >
              Line Breaks
            </h3>
            <p class="mb-6" :class="{ 'text-gray-300': darkMode, 'text-gray-600': !darkMode }">
              Elemen line break (&lt;br&gt;) digunakan untuk membuat jeda baris baru tanpa memulai
              paragraf baru.
            </p>
            <div
              class="bg-gray-100 p-4 rounded-lg"
              :class="{ 'bg-gray-800': darkMode, 'bg-gray-100': !darkMode }"
            >
              <div :class="{ 'text-white': darkMode, 'text-gray-800': !darkMode }">
                Jalan Menganti No.88,<br />
                Desa Laban,<br />
                Kota Bogor,<br />
                Indonesia 16918
              </div>
            </div>
            <div class="mt-4">
              <button
                @click="showCode('lineBreaks')"
                class="text-sm px-4 py-2 rounded-lg border"
                :class="{
                  'border-gray-600 text-gray-300 hover:bg-gray-700': darkMode,
                  'border-indigo-300 text-indigo-600 hover:bg-indigo-50': !darkMode,
                }"
              >
                {{ codeVisible.lineBreaks ? 'Sembunyikan Kode' : 'Lihat Kode' }}
              </button>
              <pre
                v-if="codeVisible.lineBreaks"
                class="mt-4 p-4 rounded-lg text-sm overflow-auto"
                :class="{
                  'bg-gray-800 text-gray-300': darkMode,
                  'bg-gray-100 text-gray-800': !darkMode,
                }"
              >
    Jalan Menganti No.88,&lt;br&gt;
    Desa Laban,&lt;br&gt;
    Kota Bogor,&lt;br&gt;
    Indonesia 16918
                  </pre
              >
            </div>
          </section>

          <!-- Horizontal Rules -->
          <section
            id="horizontal-rules"
            :class="{ 'bg-gray-900 text-white': darkMode, 'bg-white': !darkMode }"
            class="transition duration-500 rounded-lg p-6 shadow-lg transform hover:scale-[1.01]"
          >
            <h3
              class="text-2xl font-bold mb-4"
              :class="{ 'text-indigo-300': darkMode, 'text-indigo-600': !darkMode }"
            >
              Horizontal Rules
            </h3>
            <p class="mb-6" :class="{ 'text-gray-300': darkMode, 'text-gray-600': !darkMode }">
              Elemen horizontal rule (&lt;hr&gt;) digunakan untuk membuat garis horizontal yang
              memisahkan konten.
            </p>
            <div
              class="bg-gray-100 p-4 rounded-lg"
              :class="{ 'bg-gray-800': darkMode, 'bg-gray-100': !darkMode }"
            >
              <p :class="{ 'text-white': darkMode, 'text-gray-800': !darkMode }">
                Bagian pertama dari konten.
              </p>
              <hr
                class="my-4 border-t"
                :class="{ 'border-gray-600': darkMode, 'border-gray-300': !darkMode }"
              />
              <p :class="{ 'text-white': darkMode, 'text-gray-800': !darkMode }">
                Bagian kedua dari konten.
              </p>
              <hr
                class="my-4 border-t-2"
                :class="{ 'border-gray-600': darkMode, 'border-gray-300': !darkMode }"
              />
              <p :class="{ 'text-white': darkMode, 'text-gray-800': !darkMode }">
                Bagian ketiga dari konten.
              </p>
            </div>
            <div class="mt-4">
              <button
                @click="showCode('horizontalRules')"
                class="text-sm px-4 py-2 rounded-lg border"
                :class="{
                  'border-gray-600 text-gray-300 hover:bg-gray-700': darkMode,
                  'border-indigo-300 text-indigo-600 hover:bg-indigo-50': !darkMode,
                }"
              >
                {{ codeVisible.horizontalRules ? 'Sembunyikan Kode' : 'Lihat Kode' }}
              </button>
              <pre
                v-if="codeVisible.horizontalRules"
                class="mt-4 p-4 rounded-lg text-sm overflow-auto"
                :class="{
                  'bg-gray-800 text-gray-300': darkMode,
                  'bg-gray-100 text-gray-800': !darkMode,
                }"
              >
    &lt;p&gt;Bagian pertama dari konten.&lt;/p&gt;
    &lt;hr&gt;
    &lt;p&gt;Bagian kedua dari konten.&lt;/p&gt;
    &lt;hr&gt;
    &lt;p&gt;Bagian ketiga dari konten.&lt;/p&gt;
                  </pre
              >
            </div>
          </section>

          <!-- Subscript and Superscript -->
          <section
            id="sub-sup"
            :class="{ 'bg-gray-900 text-white': darkMode, 'bg-white': !darkMode }"
            class="transition duration-500 rounded-lg p-6 shadow-lg transform hover:scale-[1.01]"
          >
            <h3
              class="text-2xl font-bold mb-4"
              :class="{ 'text-indigo-300': darkMode, 'text-indigo-600': !darkMode }"
            >
              Subscript dan Superscript
            </h3>
            <p class="mb-6" :class="{ 'text-gray-300': darkMode, 'text-gray-600': !darkMode }">
              Subscript (&lt;sub&gt;) dan Superscript (&lt;sup&gt;) digunakan untuk menampilkan teks
              sedikit di bawah atau di atas garis teks normal.
            </p>
            <div
              class="bg-gray-100 p-4 rounded-lg"
              :class="{ 'bg-gray-800': darkMode, 'bg-gray-100': !darkMode }"
            >
              <p class="mb-4" :class="{ 'text-white': darkMode, 'text-gray-800': !darkMode }">
                Formula kimia air: H<sub>2</sub>O
              </p>
              <p class="mb-4" :class="{ 'text-white': darkMode, 'text-gray-800': !darkMode }">
                Rumus matematika: E = mc<sup>2</sup>
              </p>
              <p class="mb-4" :class="{ 'text-white': darkMode, 'text-gray-800': !darkMode }">
                Pangkat: 2<sup>10</sup> = 1024
              </p>
              <p :class="{ 'text-white': darkMode, 'text-gray-800': !darkMode }">
                Catatan kaki<sub>[1]</sub> biasanya menggunakan subscript.
              </p>
            </div>
            <div class="mt-4">
              <button
                @click="showCode('subSup')"
                class="text-sm px-4 py-2 rounded-lg border"
                :class="{
                  'border-gray-600 text-gray-300 hover:bg-gray-700': darkMode,
                  'border-indigo-300 text-indigo-600 hover:bg-indigo-50': !darkMode,
                }"
              >
                {{ codeVisible.subSup ? 'Sembunyikan Kode' : 'Lihat Kode' }}
              </button>
              <pre
                v-if="codeVisible.subSup"
                class="mt-4 p-4 rounded-lg text-sm overflow-auto"
                :class="{
                  'bg-gray-800 text-gray-300': darkMode,
                  'bg-gray-100 text-gray-800': !darkMode,
                }"
              >
    &lt;p&gt;Formula kimia air: H&lt;sub&gt;2&lt;/sub&gt;O&lt;/p&gt;
    &lt;p&gt;Rumus matematika: E = mc&lt;sup&gt;2&lt;/sup&gt;&lt;/p&gt;
    &lt;p&gt;Pangkat: 2&lt;sup&gt;10&lt;/sup&gt; = 1024&lt;/p&gt;
    &lt;p&gt;Catatan kaki&lt;sub&gt;[1]&lt;/sub&gt; biasanya menggunakan subscript.&lt;/p&gt;
                  </pre
              >
            </div>
          </section>

          <!-- Blockquote -->
          <section
            id="blockquote"
            :class="{ 'bg-gray-900 text-white': darkMode, 'bg-white': !darkMode }"
            class="transition duration-500 rounded-lg p-6 shadow-lg transform hover:scale-[1.01]"
          >
            <h3
              class="text-2xl font-bold mb-4"
              :class="{ 'text-indigo-300': darkMode, 'text-indigo-600': !darkMode }"
            >
              Blockquote
            </h3>
            <p class="mb-6" :class="{ 'text-gray-300': darkMode, 'text-gray-600': !darkMode }">
              Elemen blockquote (&lt;blockquote&gt;) digunakan untuk menandai bagian yang dikutip
              dari sumber lain.
            </p>
            <div
              class="bg-gray-100 p-4 rounded-lg"
              :class="{ 'bg-gray-800': darkMode, 'bg-gray-100': !darkMode }"
            >
              <blockquote
                class="border-l-4 pl-4 italic"
                :class="{
                  'border-indigo-300 text-gray-300': darkMode,
                  'border-indigo-600 text-gray-600': !darkMode,
                }"
              >
                <p class="mb-2">
                  "Jika memainkan peran apa pun dalam hidup ini, jadilah diri Anda sendiri; jangan
                  pernah meniru."
                </p>
                <footer :class="{ 'text-gray-400': darkMode, 'text-gray-500': !darkMode }">
                  — Ralph Waldo Emerson
                </footer>
              </blockquote>
            </div>
            <div class="mt-4">
              <button
                @click="showCode('blockquote')"
                class="text-sm px-4 py-2 rounded-lg border"
                :class="{
                  'border-gray-600 text-gray-300 hover:bg-gray-700': darkMode,
                  'border-indigo-300 text-indigo-600 hover:bg-indigo-50': !darkMode,
                }"
              >
                {{ codeVisible.blockquote ? 'Sembunyikan Kode' : 'Lihat Kode' }}
              </button>
              <pre
                v-if="codeVisible.blockquote"
                class="mt-4 p-4 rounded-lg text-sm overflow-auto"
                :class="{
                  'bg-gray-800 text-gray-300': darkMode,
                  'bg-gray-100 text-gray-800': !darkMode,
                }"
              >
    &lt;blockquote&gt;
      &lt;p&gt;
        "Jika memainkan peran apa pun dalam hidup ini, jadilah diri Anda sendiri; jangan pernah meniru."
      &lt;/p&gt;
      &lt;footer&gt;
        — Ralph Waldo Emerson
      &lt;/footer&gt;
    &lt;/blockquote&gt;
                  </pre
              >
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
            <h4 class="text-xl font-bold mb-4">HTML<span class="text-orange-500">Docs</span></h4>
            <p class="text-gray-400">
              Dokumentasi ini dibuat untuk tujuan pendidikan sebagai bagian dari tugas kuliah
              pemrograman web.
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
          <p>&copy; {{ new Date().getFullYear() }} HTML Documentation. Dari Tim Web GasBelajar</p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

// Menu items
const menuItems = [
  { id: 1, name: 'Headings', target: 'headings' },
  { id: 2, name: 'Paragraphs', target: 'paragraphs' },
  { id: 3, name: 'Line Breaks', target: 'line-breaks' },
  { id: 4, name: 'Horizontal Rules', target: 'horizontal-rules' },
  { id: 5, name: 'Sub & Sup', target: 'sub-sup' },
  { id: 6, name: 'Blockquote', target: 'blockquote' },
]

// Dark mode state
const darkMode = ref(false)

// Code visibility state
const codeVisible = ref({
  headings: false,
  paragraphs: false,
  lineBreaks: false,
  horizontalRules: false,
  subSup: false,
  blockquote: false,
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
