<script setup>
const contactInfo = [
  {
    id: 1,
    type: 'Phone:',
    value: '442038857261',
  },
  {
    id: 2,
    type: 'Email:',
    value: 'help@google.com',
  },
  {
    id: 3,
    type: 'Address:',
    value:
      'Trust Company Complex, Ajeltake Road, Ajeltake Island, Majuro, Republic of the Marshall Islands, MH 96960',
  },
]
</script>
<template>
  <div class="bg-violet-bg/10 flex items-center p-30 gap-33">
    <div class="w-[34%]">
      <h2 class="font-museo font-medium text-[56px] leading-[66px] text-gray mb-8">Contact us!</h2>
      <p class="font-montserrat font-normal text-lg leading-[30px] text-gray-text mb-12">
        The support staff and customer service are available to help you with any questions or needs
        you might have. Just drop us a line.
      </p>
      <p class="font-montserrat font-normal text-base leading-[27px] text-gray-text mb-6">
        This site is owned and operated by Kode Tech Solutions LTD
      </p>
      <div class="flex flex-col gap-[16px]">
        <div v-for="contact in contactInfo" :key="contact.id" class="flex flex-col gap-2">
          <p class="font-museo font-medium text-[15px] leading-4 text-gray">
            <strong>{{ contact.type }}</strong>
          </p>
          <p class="font-montserrat font-normal text-base leading-[27px] text-gray-text">
            {{ contact.value }}
          </p>
        </div>
      </div>
    </div>
    <div class="bg-white border-2 border-violet rounded-[30px] p-20 flex-grow">
      <form action="" class="flex flex-col items-center gap-6 px-4 py-[7px]">
        <div class="w-full">
          <input type="text" placeholder="Name" class="input w-full" />
          <p class="mt-2 text-[15px] font-museo leading-4 text-error hidden">
            <strong>This input is require</strong>
          </p>
        </div>
        <div class="w-full">
          <input type="email" placeholder="Email" class="input w-full" />
          <p class="mt-2 text-[15px] font-museo leading-4 text-error hidden">
            <strong>Incorrect email type</strong>
          </p>
        </div>
        <div class="w-full">
          <textarea placeholder="Message" class="input w-full min-h-[89px] max-h-30"></textarea>
          <p class="mt-2 text-[15px] font-museo leading-4 text-error hidden">
            <strong>This input is require</strong>
          </p>
        </div>

        <button class="button">Send</button>
      </form>
    </div>
  </div>
</template>
