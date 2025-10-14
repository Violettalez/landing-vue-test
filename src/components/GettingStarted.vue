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
  <div class="pt-25 pl-[120px] pr-[222px]">
    <h2 class="leading-[66px] font-museo font-medium text-[56px] w-[40%] mb-[113px]">
      Getting Started Is <span class="bg-violet-bg/10 pb-2">Fast & Easy</span>
    </h2>
    <div class="relative flex flex-col">
      <div
        v-for="instruction in intructions"
        :key="instruction.id"
        :class="` z-2 w-[483px] border-2 p-8 rounded-[30px] bg-white border-violet-bg font-medium mb-2 text-[15px] ${instruction.id % 2 === 0 ? 'self-end' : 'self-start'} mt-[-53px]`"
      >
        <p class="font-museo text-violet-bg">0{{ instruction.id }}.</p>
        <h2 class="font-museo text-2xl font-medium mb-6">{{ instruction.title }}</h2>
        <p class="font-montserrat leading-[30px] font-normal text-[18px] text-gray-text">
          {{ instruction.description }}
        </p>
      </div>
      <div
        class="absolute top-0 left-1/5 w-[60%] *:h-[200px] *:rounded-[30px] *:border-dotted *:border-violet-bg"
      >
        <div class="border-t-3 border-r-3"></div>
        <div class="border-t-3 border-l-3"></div>
        <div class="border-t-3 border-r-3"></div>
      </div>
    </div>
  </div>
</template>
<style></style>
