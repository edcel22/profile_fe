<template>
  <div class="profile_test">
    
    <TopNavigation />

    <Nuxt />

  </div>
</template>
<script>
  import TopNavigation from '~/components/global/TopNavigation'

  export default {
    components: {
      TopNavigation
    },
  }
</script>