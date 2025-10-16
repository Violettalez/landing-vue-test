<script setup>
const intructions = [
  {
    id: 1,
    title: 'Register',
    description: 'Complete the simple registration to get your trading credentials.',
  },
  {
    id: 2,
    title: 'Verification',
    description:
      'Big Invest is required to verify your identity, upload your documents quickly and get approved in minutes.',
  },
  {
    id: 3,
    title: 'Deposit funds',
    description:
      'Big Invest accepts credit cards and bank wires. Just use the secure deposit form and follow the steps.',
  },
  {
    id: 4,
    title: 'Start Trading',
    description:
      'Once your deposit has been credited, you can begin trading instantly. In no time you will see profits rolling into your account.',
  },
]
</script>
<template>
  <div class="desktop:pt-25 tablet:pt-30 mobile:pt-20 desktop:pl-[120px] desktop:pr-[222px] tablet:px-10 mobile:px-5">
    <h2
      class="leading-[66px] font-museo font-medium text-[56px] desktop:w-[40%] tablet:w-[60%] desktop:mb-[113px] tablet:mb-[111px] mobile:mb-10 text-gray"
    >
      Getting Started Is <span class="bg-violet-bg/10 pb-2">Fast & Easy</span>
    </h2>
    <div class="relative flex flex-col desktop:gap-0 tablet:gap-0 mobile:gap-6">
      <div
        v-for="instruction in intructions"
        :key="instruction.id"
        :class="` z-2 desktop:w-[483px] tablet:w-[329px] mobile:w-full border-2 p-8 rounded-[30px] bg-white border-violet-bg font-medium text-[15px] ${instruction.id % 2 === 0 ? 'desktop:self-end tablet:self-end' : 'desktop:self-start tablet:self-start'} desktop:mt-[-53px] tablet:mt-[-55px] mobile:mt-0 relative `"
      >
        <p class="font-museo text-violet-bg">0{{ instruction.id }}.</p>
        <h2 class="font-museo text-2xl font-medium mb-6 text-gray">{{ instruction.title }}</h2>
        <p class="font-montserrat leading-[30px] font-normal text-[18px] text-gray-text">
          {{ instruction.description }}
        </p>
      </div>
      <div
        class="absolute top-10 left-1/5 w-[60%] desktop:*:h-[170px] tablet:*:h-50 *:rounded-[30px] *:border-dotted *:border-violet-bg desktop:block tablet:block mobile:hidden"
      >
        <div class="border-t-3 border-r-3"></div>
        <div class="border-t-3 border-l-3"></div>
        <div class="border-t-3 border-r-3"></div>
      </div>
    </div>
  </div>
</template>
<style></style>
