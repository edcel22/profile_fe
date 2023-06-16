<template>
  <div class="tab_content">
    <!-- TAB HEADER -->
    <TabContentHeader />
    <!-- TAB BODY -->
    <TabContentBody />
  </div>
</template>
<script>
  export default {
    components: {
      TabContentHeader: () => import('~/components/tab/tab-contents/TabContentHeader'),
      TabContentBody: () => import('~/components/tab/tab-contents/TabContentBody')
    },
  }
</script>
<style lang="stylus">
  .tab_content
    display: flex
    flex-flow: column wrap
    width: 100%
    flex: 1 0 calc(100% - 220px)
</style>
