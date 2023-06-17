<template>
  <div class="profile_page">
    <div class="page_wrapper">
      <div class="tab_container">
        <!-- Tab navigation links -->
        <TabNavigation />
        <!-- Tab contents -->
        <TabContent />
      </div>
    </div>
  </div>
</template>
<script>
  export default {
    components: {
      TabNavigation: () => import('~/components/tab/TabNavigation'),
      TabContent: () => import('~/components/tab/TabContent'),
    },
  }
</script>
<style lang="stylus">
  .profile_page
    display: flex
    justify-content: center
    .page_wrapper
      width: 100%
      max-width: 1260px
      margin: 100px 20px 0
      .tab_container
        display: flex
        width: 100%
</style>

