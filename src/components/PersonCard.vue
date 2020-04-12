<template>
<div class="container mx-auto py-10">
  <div class="border m-6 rounded-lg  bg-white mx-auto max-w-sm shadow-lg rounded-lg overflow-hidden">
    <div class="sm:flex sm:items-center px-6 py-4">
      <img class="block h-16 sm:h-24 rounded-full mx-auto mb-4 sm:mb-0 sm:mr-4 sm:ml-0" src="https://max.berlin/assets/images/max.svg" alt="">
      <div class="text-center sm:text-left sm:flex-grow">
        <div class="mb-4">
          <p class="text-xl leading-tight">{{ name }}</p>
          <p class="text-sm leading-tight text-grey-dark">{{title}}</p>
        </div>
        <div class="flex flex-wrap">
          <a :href="website" class="text-xs font-semibold rounded-full px-4 py-1 mx-3  leading-normal bg-white border border-blue-500 text-blue-500 hover:bg-blue-500 hover:text-white">Website</a>
          <a :href="handle" class="text-xs font-semibold rounded-full px-4 py-1 leading-normal bg-white border border-purple-500 text-purple-500 hover:bg-purple-500 hover:text-white">Message</a>
        </div>
      </div>
    </div>
  </div>
</div>
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
