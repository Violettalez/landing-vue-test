<script setup>
import { ref } from 'vue'
import person1 from '../assets/person1.png'

const quotes = [
  {
    id: 1,
    name: 'Albert Abello',
    position: 'Director of Growth',
    quote:
      'This magical product actually works! It has radically changed the way we build our audiences. Increasing new customer sales by 6x in our most mature market.',
    image: person1,
  },
  {
    id: 2,
    name: 'John Doe',
    position: 'Financial Advisor at XYZ Financial',
    quote:
      "As a financial advisor, I rely on Big Invest to provide my clients with the best investment options. The platform's comprehensive analysis and real-time data have been invaluable in helping my clients achieve their financial goals.",
    image: 'https://randomuser.me/api/portraits/men/74.jpg',
  },
  {
    id: 3,
    name: 'Emily Smith',
    position: 'Individual Investor',
    quote:
      "I started using Big Invest a year ago, and it has been a game-changer for me. The platform's intuitive design and powerful tools have made investing accessible and enjoyable. I've seen great returns on my investments thanks to Big Invest.",
    image: 'https://randomuser.me/api/portraits/men/72.jpg',
  },
  {
    id: 4,
    name: 'Michael Johnson',
    position: 'Portfolio Manager at DEF Investments',
    quote:
      "Big Invest offers a level of insight and analysis that is unmatched in the industry. The platform's advanced algorithms and data-driven approach have helped me optimize my clients' portfolios and deliver exceptional results.",
    image: 'https://randomuser.me/api/portraits/men/71.jpg',
  },
]

const choosedQuote = ref(quotes[0])
function nextQuote() {
  const currentIndex = quotes.findIndex((quote) => quote.id === choosedQuote.value.id)
  const nextIndex = (currentIndex + 1) % quotes.length
  choosedQuote.value = quotes[nextIndex]
}
function prevQuote() {
  const currentIndex = quotes.findIndex((quote) => quote.id === choosedQuote.value.id)
  const prevIndex = (currentIndex - 1 + quotes.length) % quotes.length
  choosedQuote.value = quotes[prevIndex]
}
</script>
<template>
  <section class="flex px-30 py-40 gap-21">
    <div class="flex flex-col gap-[47px]">
      <h2 class="leading-[66px] font-museo font-medium text-[56px]">
        People love Big
        <span class="bg-violet-bg/10 pb-2"
          >Invest <span class="text-violet-bg/0">Invest</span></span
        >
      </h2>
      <div
        class="*:rounded-full *:w-12 *:h-12 *:border-[1px] *:border-gray-light *:hover:border-violet-bg *:flex *:items-center *:justify-center flex gap-4"
      >
        <div @click="prevQuote">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
            <path
              fill="currentColor"
              d="m10.828 12l4.95 4.95l-1.414 1.415L8 12l6.364-6.364l1.414 1.414z"
            />
          </svg>
        </div>
        <div @click="nextQuote">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
            <path
              fill="currentColor"
              d="m13.172 12l-4.95-4.95l1.414-1.413L16 12l-6.364 6.364l-1.414-1.415z"
            />
          </svg>
        </div>
      </div>
    </div>
    <div
      v-for="quote in quotes"
      :key="quote.id"
      :class="`w-[80%] mt-10 flex flex-col gap-[17px] ${choosedQuote.id === quote.id ? 'block' : 'hidden'}`"
    >
      <div class="flex items-center gap-[30px] ml-12">
        <img :src="quote.image" :alt="quote.name" class="rounded-full w-[73px]" />
        <div class="flex flex-col">
          <p class="font-museo text-lg leading-[30px] font-bold text-gray">{{ quote.name }}</p>
          <p class="font-montserrat text-base leading-[27px] font-normal text-gray-text">
            {{ quote.position }}
          </p>
        </div>
      </div>
      <div class="flex items-start gap-[15px] flex-grow">
        <img src="../assets/quote.svg" alt="quote" />
        <div class="flex flex-col gap-[31px]">
          <p class="font-museo font-bold text-2xl text-gray">{{ quote.quote }}</p>
          <p class="font-museo font-bold text-[15px] text-violet-bg">
            0{{ quote.id }} / 0{{ quotes.length }}
          </p>
        </div>
      </div>
    </div>
  </section>
</template>
