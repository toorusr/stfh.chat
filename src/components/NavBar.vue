<template>
<nav class="p-6 md:py-0 md:px-10 mb-16 md:mt-10 flex justify-between flex-row">
  <router-link to="/"><div class="flex flex-row">
    <img class="h-12 md:h-10 mr-4" src="@/assets/img/logo.svg" />
    <p class="hidden md:block bree text-green-400 my-auto text-xs">Stay the fuck home</p>
  </div></router-link>
  <div class="flex flex-row">
    <img class="mx-2 h-12 md:h-10" src="@/assets/img/app-store.svg" />
    <img class="hidden md:block h-10" src="@/assets/img/play-store.svg" />
  </div>
</nav>
</template>

<script>
export default {
  name: 'NavBar',
}
</script>
