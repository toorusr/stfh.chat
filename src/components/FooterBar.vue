<template>
  <footer class="px-10 mt-16 my-8">
    <div class="flex justify-between flex-row mt-4">
      <div class="text-xs montserrat flex flex-row">
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
    </div>
  </footer>
</template>

<script>
export default {
  name: 'PersonCard',
  props: {
    name: String,
    title: String,
    website: String,
    handle: String,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
