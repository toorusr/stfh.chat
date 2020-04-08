<template>
  <div class="">
    <PersonCard name="Maximilian Jendrall" title="Polyfounder and developer" website="https://max.berlin" handle="https://t.me/toorusr"/>
  </div>
</template>

<script>
// @ is an alias to /src
import PersonCard from '@/components/PersonCard.vue'

export default {
  name: 'Home',
  components: {
    PersonCard
  }
}
</script>
