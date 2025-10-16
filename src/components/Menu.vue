<script setup>
import { ref } from 'vue'

const langs = ['EN', 'UA']
const currentLang = ref(langs[0])
const isOpen = ref(false)

function toggleLangSelection() {
  isOpen.value = !isOpen.value
}

function selectLang(lang) {
  currentLang.value = lang
  isOpen.value = false
}
</script>

<template>
  <nav
    class="flex justify-between items-center desktop:py-5 tablet:py-5 tablet:px-10 desktop:px-15 mobile:px-5 mobile:py-[30px]"
  >
    <div class="flex gap-14.25 items-center desktop:ml-15">
      <h1
        class="desktop:block tablet:hidden mobile:block cursor-pointer font-museo font-extrabold text-[15px] text-gray"
      >
        LOGO
      </h1>
      <ul
        class="desktop:flex hidden items-center gap-4 justify-between *:font-museo *:font-medium *:text-[15px] *:text-gray"
      >
        <li><a href="#">How it works</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Instractions</a></li>
        <li><a href="#">Accounts</a></li>
        <li><a href="#">Platforms</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </div>

    <div
      class="flex items-center desktop:gap-5 gap-12 desktop:justify-start justify-end desktop:w-auto w-full"
    >
      <div class="relative desktop:block hidden">
        <button
          @click="toggleLangSelection"
          class="font-museo font-medium text-[15px] flex items-center gap-1 text-gray border border-black rounded-[60px] py-2.5 px-4 cursor-pointer"
        >
          {{ currentLang }}
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="w-4 h-4 text-black"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M19 9l-7 7-7-7"
            />
          </svg>
        </button>

        <ul
          v-if="isOpen"
          class="absolute mt-2 right-0 w-20 bg-white border border-gray-200 rounded-lg shadow-md text-center"
        >
          <li
            v-for="lang in langs"
            :key="lang"
            @click="selectLang(lang)"
            class="px-2.5 py-1 hover:bg-gray-100 cursor-pointer"
          >
            {{ lang }}
          </li>
        </ul>
      </div>

      <button class="py-[13px] px-[24px] button text-sm tablet:block hidden desktop:block">
        Sign in for free
      </button>
      <img
        src="../assets/menu.svg"
        alt="navigation"
        class="desktop:hidden block w-6 h-6 cursor-pointer"
      />
    </div>
  </nav>
</template>
