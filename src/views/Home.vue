<template>
<div class="p-6 md:p-10 bg-right-top bg-cover bg-image bg-no-repeat">
  <nav class="flex justify-between md:justify-start flex-row">
    <img class="h-12 mr-10" src="@/assets/img/logo.svg" />
    <img class="mx-2 h-12" src="@/assets/img/app-store.svg" />
    <img class="hidden md:block h-12" src="@/assets/img/play-store.svg" />
  </nav>
  <div class="flex flex-col justify-center md:block mt-16 text-left w-full bree">
    <img class="block md:hidden" src="@/assets/img/chat.svg">
    <h1 class="text-3xl text-center md:text-left md:text-6xl text-green-400">Stay the fuck home</h1>
    <p class="text-xs text-green-400 text-center md:text-left">and save lifes*</p>
    <h2 class="opacity-50 text-green-400 text-xl md:text-5xl mt-6 mb-8"> The chat app for the heroes which<br> <a href="https://staythefuckhome.com/?ref=stfh.chat" class="underline">stay the fuck home</a> and <br> save the humanity. </h2>
    <div class="flex justify-center md:block">
      <router-link to="/about" class="px-10 py-2 bg-green-400 opacity-50 text-white rounded-lg text-xl hover:opacity-100 ">more info</router-link>
    </div>
  </div>
  <footer class="mt-16 md:mt-32 xl:mt-64 xl:pt-64">
    <div class="flex mb-16 flex-wrap justify-center my-8 md:hidden">
      <img class="opacity-50 mx-4" src="@/assets/img/withlove.svg" />
      <a href="https://max.berlin/p/stfh.chat"><img class="opacity-50 hover:opacity-100 mx-4" src="@/assets/img/max.berlin.svg" /></a>
      <img class="opacity-50 mr-4" src="@/assets/img/&.svg" />
      <a href="https://dnd.one/?ref=https://stfh.chat"><img class="opacity-50 hover:opacity-100" src="@/assets/img/dnd.svg" /></a>
    </div>
    <p class="bree text-left opacity-50 max-w-xs">*We are giving away 80% of the overall earnings and donate it to the WHO Responsiblity Fund for COVID-19. So you are technically really supporting the humanity.</p>
    <div class="flex justify-between flex-row mt-4">
      <div class="text-xs montserrat flex flex-wrap md:flex-row justify-center md:justify-left">
        <p class="my-auto text-green-400">&copy; 2020 STFH</p>
        <div class="flex text-green-400 ml-4 flex-row">
          <router-link class="opacity-50 mx-2 hover:opacity-100 my-auto" to="/imprint">IMPRINT</router-link>
          <router-link class="opacity-50 mx-2 hover:opacity-100 my-auto" to="/privacy">PRIVACY</router-link>
          <router-link class="opacity-50 mx-2 hover:opacity-100 my-auto" to="/contact">CONTACT</router-link>
          <router-link class="opacity-50 mx-2 hover:opacity-100 my-auto" to="/press">PRESS</router-link>
        </div>
        <div class="flex flex-row">
          <select class="text-green-400 opacity-50 appearance-none" id="lang">
            <option>EN</option>
            <option>DE</option>
            <option>ZH</option>
          </select>
          <svg fill="currentColor" viewBox="0 0 20 20" class="w-2 h-2 my-auto text-green-400 opacity-50">
            <path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd"></path>
          </svg>
        </div>
      </div>
      <div class="hidden md:flex flex-row">
        <img class="opacity-50 mx-4" src="@/assets/img/withlove.svg" />
        <a href="https://max.berlin/p/stfh.chat"><img class="opacity-50 hover:opacity-100 mx-4" src="@/assets/img/max.berlin.svg" /></a>
        <img class="opacity-50 mr-4" src="@/assets/img/&.svg" />
        <a href="https://dnd.one/?ref=https://stfh.chat"><img class="opacity-50 hover:opacity-100" src="@/assets/img/dnd.svg" /></a>
      </div>
    </div>
  </footer>
</div>
</template>
<script>
export default {
  data() {
    return {
    };
  }
};
</script>

<style>
.bree {
  font-family: 'Bree Serif', serif;
}

.montserrat {
  font-family: 'Montserrat', sans-serif;
  font-weight: 700;
}

.bg-image {
  background: url('~@/assets/img/home.svg')
}
@media only screen and (max-width: 1042px) {
  .bg-image {
    background-image: none;
  }
}

</style>
