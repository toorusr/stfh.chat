<template>
  <div>
    <NavBar />
    <div class="text-left px-20">
      <h1 class="text-5xl bree text-green-400">PRIvaCY</h1>
      <p class="opacity-50 bree text-green-400">Privacy usualy cost a lot. But in our case it’s just your <br>contribution to the help of the world, which gets you your <br>privacy rights and available options.</p>
      <p class="mt-2 opacity-50 bree text-green-400">Too lazy to read the long ass privacy policy?</p>
      <ul class="mt-2 ml-4 list-disc opacity-50 bree text-green-400">
        <li>We are GDPR complient</li>
        <li>We are OpenSource</li>
        <li>Your data is yours, delete it if you want to</li>
        <li>No we don’t sell your data</li>
      </ul>
      <div @click="longVersion = !longVersion" class="w-1/3 mt-16">
        <div class="mt-3 rounded-full justify-center hover:opacity-75 p-2 bg-white shadow-md border flex flex-row">
          <svg width="23" height="23" viewBox="0 0 23 23" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path fill-rule="evenodd" clip-rule="evenodd" d="M16.9131 14.6131C16.6974 14.8286 16.4049 14.9498 16.1 14.9498C15.7951 14.9498 15.5026 14.8286 15.287 14.6131L11.5 10.8261L7.71305 14.6131C7.60697 14.7229 7.48007 14.8105 7.33977 14.8708C7.19946 14.931 7.04856 14.9628 6.89586 14.9641C6.74317 14.9654 6.59173 14.9363 6.4504 14.8785C6.30907 14.8207 6.18067 14.7353 6.0727 14.6273C5.96472 14.5193 5.87933 14.3909 5.82151 14.2496C5.76368 14.1083 5.73458 13.9568 5.73591 13.8041C5.73724 13.6514 5.76896 13.5005 5.82923 13.3602C5.8895 13.2199 5.97711 13.093 6.08695 12.987L10.687 8.38695C10.9026 8.17136 11.1951 8.05025 11.5 8.05025C11.8049 8.05025 12.0974 8.17136 12.3131 8.38695L16.9131 12.987C17.1286 13.2026 17.2498 13.4951 17.2498 13.8C17.2498 14.1049 17.1286 14.3974 16.9131 14.6131Z" fill="#6FD786"/>
          </svg>
          <p class="text-green-400 ml-4 my-auto montserrat text-xs">View the long version</p>
        </div>
      </div>
      <div v-if="longVersion">
        <PrivacyText class=" w-2/3 text-green-400 text-xs montserrat mt-8" />
      </div>
    </div>
    <FooterBar />
  </div>
</template>

<script>
  import NavBar from '@/components/NavBar.vue'
  import FooterBar from '@/components/FooterBar.vue'
  import PrivacyText from '@/components/PrivacyText.vue'

  export default {
    name: 'privacy',
    data: () => {
      return {
        longVersion: false
      }
    },
    components: {
      NavBar,
      FooterBar,
      PrivacyText
    }
  }
</script>
