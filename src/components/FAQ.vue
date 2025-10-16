<script setup>
import { ref } from 'vue'
import { Icon } from '@iconify/vue'

const faqItems = [
  {
    id: 1,
    question: 'How do I change my details?',
    answer:
      'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
  },
  {
    id: 2,
    question: 'What platforms will I be able to use?',
    answer:
      'We provide only the best trading software. The trading terminal MetaTrader4 is the most popular and convenient platform for access to global exchanges. You can work anywhere. All you need is the Internet because the necessary trading tools are already collected in one place and are available in a couple of clicks. Use only the best and develop with us!',
  },
  {
    id: 3,
    question: 'How do I change my details?',
    answer:
      'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
  },
  {
    id: 4,
    question: 'How do I change my details?',
    answer:
      'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
  },
  {
    id: 5,
    question: 'How do I change my details?',
    answer:
      'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
  },
  {
    id: 6,
    question: 'How do I change my details?',
    answer:
      'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
  },
]
const isOpen = ref(0)
const toggle = (id) => {
  isOpen.value = isOpen.value === id ? 0 : id
}
</script>
<template>
  <div class="desktop:px-[120px] tablet:px-10 mobile:px-5 desktop:mb-[140px] tablet:mb-30 mobile:mb-20">
    <h2 class="leading-[66px] font-museo font-medium text-[56px] desktop:w-[40%] tablet:w-auto mobile:w-auto desktop:mb-15 tablet:mb-14 mobile:mb-8 text-gray">
      Frequently asked <span class="bg-violet-bg/10 pb-2">questions</span>
    </h2>
    <div class="flex flex-col gap-4 desktop:px-[102px]">
      <div
        v-for="item in faqItems"
        :key="item.id"
        class="border-2 desktop:py-8 tablet:py-8 desktop:px-10 tablet:px-10 mobile:px-8 mobile:py-6 rounded-[20px] bg-white border-violet-bg font-medium text-[15px]"
      >
        <div class="flex justify-between items-center desktop:gap-[133px] tablet:gap-[107px] mobile:gap-[27px]">
          <p class="font-museo desktop:text-2xl tablet:text-2xl mobile:text-lg font-bold text-gray">{{ item.question }}</p>
          <Icon
            icon="ri:add-fill"
            :class="`inline-block w-8 h-8 cursor-pointer ${isOpen === item.id ? 'rotate-45' : ''} transition`"
            @click="toggle(item.id)"
          />
        </div>

        <p
          :class="`desktop:pr-[165px] tablet:pr-[50px] mobile:pr-2 mt-6 font-montserrat leading-[27px] font-normal text-base text-gray-text ${isOpen === item.id ? 'block' : 'hidden'} transition`"
        >
          {{ item.answer }}
        </p>
      </div>
    </div>
  </div>
</template>
