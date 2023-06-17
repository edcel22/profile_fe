<template>
  <div class="details">
    <div class="edit_action">
      <div v-html="edit_icon"></div>
    </div>
    <div class="detail_title">{{ detail.title }}</div>
    <div class="fields">
      <div class="group" v-for="(item, index) in detail.fields">
        <p class="label">{{ item.label }}</p>
        <p class="value">{{ (item.value) ? item.value : '-' }}</p>
      </div>
    </div>
  </div>
</template>
<script>
  import { mapGetters } from 'vuex'

  export default {
    props: {
      detail: {
        type: Object,
        default: null
      }
    },
    computed: {
      ...mapGetters({
        edit_icon: 'settings/svg/getEditIcon',
      })
    }
  }
</script>
<style lang="stylus">
  .details
    position: relative
    padding: 20px
    border-bottom: 1.5px solid rgba(0,0,0,0.122)
    &:last-child
      border-bottom: unset
    .detail_title
      font-size: 15px
    .fields
      .group
        display: flex
        align-items: center
        justify-content: flex-start
        padding-top: 20px
        .label
          font-size: 13px
          flex: 0 0 33.33%
        .value
          font-size: 14px
          flex: 1 0 calc(100% - 33.33%)
    .edit_action
      position: absolute
      top: 20px
      right: 20px
      width: 20px
      cursor: pointer
      svg
        path
          fill: #505669
</style>