<template>
  <!--
    This example requires updating your template:

    ```
    <html class="h-full bg-gray-100">
    <body class="h-full">
    ```
  -->
  <div class="z-[100] absolute w-full h-16">
    <Disclosure as="nav" class="bg-[#18191B]" style="-webkit-app-region: drag">
      <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
        <div class="flex h-12 items-center justify-between">

          <div class="flex items-center">
            <div class="flex-shrink-0">
              <img class="h-7 w-7" src="https://i.ibb.co/F34tqJT/logo.png" alt="Your Company" />
            </div>
            <div class="">
              <div class="ml-2 flex items-center space-x-4 text-white text-lg text-center ">
                <h1>EZFPS</h1>
              </div>
            </div>
          </div>
          <div class="">
            <div class="ml-4 flex items-center md:ml-6">


              <!-- Profile dropdown -->

            </div>
          </div>

          <div class="-mr-2 flex">

            <div class="inline-flex items-center space-x-4 text-gray-400" style="-webkit-app-region: no-drag;">

              <!-- Mobile menu button -->
              <div class="" v-if="user">


              </div>
              <div class="px-5" v-if="user">
                <span class="px-5 border-gray-500 py-1 rounded-sm">{{ user.email }}</span>
              </div>
              <button @click="minimize">
                <svg class="w-5 h-6" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="#FFFFFF"
                  viewBox="0 0 18 2">
                  <path stroke="#FFFFFF" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 1h16" />
                </svg>
              </button>
              <button v-if="user" id="btn_log_out" @click="SignOut">
                <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" viewBox="0 0 24 24">
                  <path fill="#FFFFFF"
                    d="M5 21q-.825 0-1.413-.588T3 19V5q0-.825.588-1.413T5 3h7v2H5v14h7v2H5Zm11-4l-1.375-1.45l2.55-2.55H9v-2h8.175l-2.55-2.55L16 7l5 5l-5 5Z" />
                </svg>
              </button>
              <button @click="quit" class="cursor-pointer">
                <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" viewBox="0 0 20 20">
                  <path fill="#FFFFFF"
                    d="m12 13.4l-4.9 4.9q-.275.275-.7.275t-.7-.275q-.275-.275-.275-.7t.275-.7l4.9-4.9l-4.9-4.9q-.275-.275-.275-.7t.275-.7q.275-.275.7-.275t.7.275l4.9 4.9l4.9-4.9q.275-.275.7-.275t.7.275q.275.275.275.7t-.275.7L13.4 12l4.9 4.9q.275.275.275.7t-.275.7q-.275.275-.7.275t-.7-.275L12 13.4Z" />
                </svg></button>
            </div>
          </div>
        </div>
      </div>

    </Disclosure>



  </div>
</template>

<script setup>
import { Disclosure } from '@headlessui/vue'
const supabase = useSupabaseClient();
let { data: { session } } = await supabase.auth.getSession()
const user = useSupabaseUser()

async function SignOut() {
  const { error } = await supabase.auth.signOut();
  session = null;
  if (error) {
    throw error;
  }
  console.log("signout");
  navigateTo("/signin");
}
supabase.auth.onAuthStateChange((e)=>{
  console.log(e)
})
</script>
<script>

import { ref } from 'vue';
const quit = () => {
  electronAPI.quit();
}

const minimize = () => {
  electronAPI.minimize();
}
</script>

