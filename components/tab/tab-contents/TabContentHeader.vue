<template>
  <div class="tab_header box">
    <div class="box_top">
      <h2>Welcome, Reyven!</h2>
      <p><span>You're almost done!</span> To further strengthen your profile, it is highly recommmended for you to complete the 4 s ections of your applciation</p>
    </div>
    <div class="box_bottom">
      <ul>
        <li v-for="(item, index) in  profile_processes">
          <div class="link_icon" v-html="item.icon"></div>
          <div class="extras">
            <p>{{ item.label }}</p>
            <div class="progress mid">
              <div class="line">
                <div class="line_prog"></div>
              </div>
              <span class="percentage" style="top: -4px; right: -37px;">50%</span>
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
        profile_processes: 'data/links/getProfileProcesses'
      })
    },
  }
</script>
<style lang="stylus">
  .tab_header
    .box_top
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