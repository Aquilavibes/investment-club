<template>
<div class="min-h-screen flex items-center justify-center bg-blue-50 px-4">
    <!-- Container -->
    <div class="bg-white shadow-lg rounded-lg p-8 w-full max-w-md sm:max-w-sm lg:max-w-lg">
      <!-- Header -->
      <h1 class="text-2xl font-semibold text-blue-600 text-center mb-6">
        Access Code Login
      </h1>

      <!-- Form -->
      <form @submit.prevent="handleRoute">
        <!-- Access Code Input -->
        <div class="mb-4">
          <label for="accessCode" class="block text-sm font-medium text-gray-700 mb-2">
            Access Code
          </label>
          <input
            type="text"
            id="accessCode"
            v-model="accessCode"
            placeholder="Enter your access code"
            class="w-full border border-gray-300 rounded-lg p-3 focus:outline-none focus:ring-2 focus:ring-blue-500"
          />
        </div>

        <!-- Submit Button -->
        <button
          type="submit"
          class="w-full bg-blue-600 text-white font-medium py-3 rounded-lg hover:bg-blue-700 transition"
        >
          Submit
        </button>
      </form>
    </div>
  </div>
</template>
<script setup>
import { ref } from 'vue';
import { useRouter}  from 'vue-router'
const errMsg = ref('')
const accessCode = ref('')
const route = useRouter()

const handleRoute = () => {
  if (accessCode.value == '1964') {
    route.push('/login')
  } else {
    errMsg.value = 'Wrong access code'
    route.push('/')
  }
}

</script>

<style scoped>
#errMsg {
    background-color: rgb(219, 114, 114);
    width: 230px;
    height: 25px;
    border-radius: 5px;
    padding-top: 10px;
    
}



</style>