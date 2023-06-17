<template>
  <ul>
    <li v-for="(item, index) in items">
      <nuxt-link to="" 
        :exact-active-class="(item.slug == 'profile') ? 'exact' : ''" 
        :active-class="(item.slug == 'profile') ? 'active' : ''"
      >
        <div class="link_icon" v-html="item.icon"></div>
        <span>{{ item.tab_name }}</span>
      </nuxt-link>
    </li>
  </ul>
</template>
<script>
  export default {
    props: {
      items: {
        type: Array,
        default: [],
        required: true
      }
    }
  }
</script>
<style lang="stylus" scoped>
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
</style>