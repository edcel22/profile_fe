<template>
  <div class="tab_header box">
    <div class="box_top">
      <h2>Welcome, {{ user_firstname }}!</h2>
      <div v-html="reminder.message"></div>
      <div class="actions">
        <div class="group">
          <input type="checkbox" name="reminder" v-model="is_remind">
          <label for="reminder">Don't remind me again</label>
        </div>
        <div class="close" v-html="close_icon"></div>
      </div>
    </div>
    <div class="box_bottom">
      <ul>
        <li v-for="(item, index) in  profile_processes">
          <div class="link_icon" v-html="item.icon"></div>
          <div class="extras">
            <p>{{ item.label }}</p>
            <div :class="`progress ${(item.percentage <= 33.33) ? 'low' : (item.percentage <= 99) ? 'mid' : 'success'}`">
              <div class="line">
                <div class="line_prog"></div>
              </div>
              <span class="percentage" style="top: -4px; right: -37px;">{{item.percentage}}%</span>
            </div>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
  import { mapGetters } from 'vuex'

  export default {
    computed: {
      ...mapGetters({
        profile_processes: 'data/links/getProfileProcesses',
        close_icon: 'settings/svg/getCloseIcon',
      })
    },
    data() {
      return {
        user_firstname:'Edcel',
        reminder: {
          message: "<p><span>You're almost done!</span> To further strengthen your profile, it is highly recommmended for you to complete the 4 s ections of your applciation</p>"
        },
        is_remind: false
      }
    }
  }
</script>
<style lang="stylus">
  .tab_header
    .box_top
      position: relative
      padding: 25px 25px 20px
      border-bottom: 1.5px solid #0000001f
      h2
        font-size: 22px
        margin-bottom: 10px
      p
        font-size: 14px
        font-weight: 300
        span
          color: #21C55E
      .actions
        display: flex
        align-items: center
        position: absolute
        top: 10px
        right: 10px
        .group
          display: flex
          align-items: center
          label
            font-size: 13px
            font-weight: 300
            color: #505669
            margin: 0 10px 0 5px
        .close
          color: #FF6161
          width: 15px
          height: 15px
          cursor: pointer
          svg
            width: 100%
            fill: #ff6161
    .box_bottom
      padding: 20px
      ul
        display: flex
        li
          display: flex
          align-items: center
          flex: 1 0 25%
          .link_icon
            width: 40px
            height: 40px
            border-radius: 100%
            background: #EFF2F7
            display: flex
            align-items: center
            justify-content: center
            margin-right: 10px
          p
            font-weight: 400
            font-size: 15px
            margin-bottom: 10px
</style>