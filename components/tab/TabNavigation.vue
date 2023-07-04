<template>
  <div class="tabs_navigation">
    <div class="applicant_profile">
      <Links 
        :items="profile_processes"
      />
    </div>
    <div class="tab_links">
      <Links 
        :items="navigation_links"
      />
      {{ wlsjkldfs }}
    </div>
    <div class="short_info"
      <p>Copyright 2018 - 2023. All Rights Reserved</p>
      <div class="links">
        <nuxt-link to="">Terms of Use</nuxt-link>
        <nuxt-link to="">Privacy Policy</nuxt-link>
      </div>
    </div>
  </div>
</template>
<script>
  import { mapGetters } from 'vuex'
  import Links from '~/components/tab/tab-navigation/Links'

  export default {
    components: {
      Links
    },
    computed: {
      ...mapGetters({
        profile_processes: 'data/links/getProfileProcesses',
        navigation_links: 'data/links/getNavigationLinks'
      })
    },
  }
</script>
<style lang="stylus">
  .tabs_navigation
    width: 100%
    flex: 1 0 calc(220px - 20px)
    margin-right: 20px
    .applicant_profile
      padding: 10px 0
      border-bottom: 1px solid #00000021
    .tab_links
      padding: 10px 0
    .short_info
      font-size: 12px
      .links
        display: flex
        padding-top: 5px
        a
          dispaly: block
          color: #3656F5
          &:first-child
            margin-right: 10px
</style>