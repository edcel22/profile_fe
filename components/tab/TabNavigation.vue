<template>
  <div class="tabs_navigation">
    <div class="applicant_profile">
      <ul>
        <li v-for="(item, index) in profile_processes">
          <nuxt-link to="" :exact-active-class="(item.slug == 'profile') ? 'exact' : ''" :active-class="(item.slug == 'profile') ? 'active' : ''">
            <div class="link_icon" v-html="item.icon"></div>
            <span>{{ item.tab_name }}</span>
          </nuxt-link>
        </li>
      </ul>
    </div>
    <div class="tab_links">
      <ul>
        <li v-for="(link, index) in navigation_links">
          <nuxt-link to="">
            <img :src="link.icon" alt="">
            <div class="link_icon" v-html="link.icon"></div>
            <span>{{ link.label }}</span>
          </nuxt-link>
        </li>
      </ul>
    </div>
    <div class="short_info">
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

  export default {
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
    ul
      li
        a
          position: relative
          display: flex
          align-items: center
          padding: 10px
          border-radius: 5px
          overflow: hidden
          .link_icon
            display: inherit
            align-items: inherit
            margin-right: 10px
            svg
              path
                fill: #505669
          &.active
            color: #3656f5
            background: #EFF2F7
            svg
              path
                fill: #3656f5
            &:before
              content: '>'
              position: absolute
              top: 10px
              right: 0
              width: 20px
              height: 20px
          &:hover
            background: #EFF2F7
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