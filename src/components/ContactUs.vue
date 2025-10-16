<script setup>
import { ref } from 'vue'
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

const form = ref({
  name: '',
  email: '',
  message: '',
})

const errors = ref({
  name: '',
  email: '',
  message: '',
})

const touched = ref({
  name: false,
  email: false,
  message: false,
})

const validateEmail = (email) => {
  const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/
  return re.test(String(email).toLowerCase())
}
const validateName = (name) => {
  const re = /^([А-ЯЁA-Z][а-яёa-zA-Z]+)(\s[А-ЯЁA-Z][а-яёa-zA-Z]+)*$/
  return re.test(String(name))
}
const validateForm = () => {
  errors.value = {
    name: '',
    email: '',
    message: '',
  }
  let isValid = true

  if (!form.value.name || !validateName(form.value.name)) {
    isValid = false
    errors.value.name = 'Incorrect name'
    touched.value.name = true
  }

  if (!form.value.email || !validateEmail(form.value.email)) {
    isValid = false
    errors.value.email = 'Incorrect email type'
    touched.value.email = true
  }
  if (!form.value.message) {
    isValid = false
    errors.value.message = 'This input is required'
    touched.value.message = true
  }
  if (isValid) {
    alert('Form submitted successfully!')
    form.value = { name: '', email: '', message: '' }
    errors.value = { name: '', email: '', message: '' }
    touched.value = { name: false, email: false, message: false }
  }
}
</script>
<template>
  <div
    class="bg-violet-bg/10 flex justify-between desktop:flex-row tablet:flex-col mobile:flex-col items-center desktop:p-30 tablet:py-12 tablet:px-[130px] mobile:py-12 mobile:px-5 desktop:gap-[132px] tablet:gap-12 mobile:gap-12"
  >
    <div class="desktop:w-[34%] tablet:w-full mobile:w-full">
      <h2 class="font-museo font-bold text-[56px] leading-[66px] desktop:text-start tablet:text-center mobile:text-start text-gray mb-8">Contact us!</h2>
      <p class="font-montserrat text-lg text-gray-text desktop:mb-12 tablet:mb-8 leading-[30px] mobile:mb-6">
        The support staff and customer service are available to help you with any questions or needs
        you might have. Just drop us a line.
      </p>
      <p class="font-montserrat text-base text-gray-text mb-6 leading-[27px]">This site is owned and operated by Kode Tech Solutions LTD</p>
      <div class="flex flex-col gap-4">
        <div v-for="contact in contactInfo" :key="contact.id" class="flex flex-col gap-2">
          <p class="font-museo font-bold text-[15px] text-gray">
            {{ contact.type }}
          </p>
          <p class="font-montserrat text-base text-gray-text">{{ contact.value }}</p>
        </div>
      </div>
    </div>

    <div
      class="bg-white border-2 border-violet rounded-[30px] p-20 desktop:w-[585px] tablet:w-full mobile:w-full tablet:py-20 tablet:px-[41px] mobile:py-12 mobile:px-4"
    >
      <form @submit.prevent="validateForm" class="flex flex-col items-center gap-6 px-4 py-[7px]">
        <div class="w-full">
          <input
            type="text"
            placeholder="Name"
            v-model="form.name"
            :class="`input w-full ${
              touched.name ? (errors.name ? 'border-error' : 'border-ok') : ''
            }`"
          />
          <p :class="`mt-2 text-[15px] text-error ${errors.name ? 'block' : 'hidden'}`">
            <strong>{{ errors.name }}</strong>
          </p>
        </div>

        <div class="w-full">
          <input
            type="email"
            placeholder="Email"
            v-model="form.email"
            :class="`input w-full ${
              touched.email ? (errors.email ? 'border-error' : 'border-ok') : ''
            }`"
          />
          <p :class="`mt-2 text-[15px] text-error ${errors.email ? 'block' : 'hidden'}`">
            <strong>{{ errors.email }}</strong>
          </p>
        </div>

        <div class="w-full">
          <textarea
            placeholder="Message"
            v-model="form.message"
            :class="`input w-full min-h-[89px] ${
              touched.message ? (errors.message ? 'border-error' : 'border-ok') : ''
            }`"
          ></textarea>
          <p :class="`mt-2 text-[15px] text-error ${errors.message ? 'block' : 'hidden'}`">
            <strong>{{ errors.message }}</strong>
          </p>
        </div>

        <button class="button w-auto">Send</button>
      </form>
    </div>
  </div>
</template>
