<template>
  <div class="tab_body">
    <div class="main_details box">
      <!-- Introduction Details -->
      <IntroductionDetail />
      <!-- General Details -->
      <Detail :detail="profile.general_details" />
      <!-- Professional Status -->
      <Detail :detail="profile.professional_status" />
      <!-- Preference -->
      <Detail :detail="profile.preferences" />
    </div>

    <div class="extra_details">
      <section id="video_introduction" class="box">
        <div class="title">Video Introduction</div>
        <div class="vid_thumbnail">
          <img src="vid_thumbnail.png" alt="">
        </div>
      </section>

      <section id="profile_completion" class="box padding">
        <div class="title">Profile Completion</div>
        <ProgressBar 
          :percentage="100"
          :is_label_below="true"
        />
        <div class="success_message">
          <h2 class="label">Well done, Reyven!</h2>
          <img src="/success_icon.png" alt="">
          <div class="message" v-html="profile.note"></div>
        </div>
      </section>

      <section id="profile_completion" class="box padding">
        <div class="title">Profile Completion</div>
        <ProgressBar 
          :percentage="50"
          :is_label_below="true"
        />
        <div class="recommendation_container">
          <div class="reco_title" @click="show_reco ^= true">Show Recommendation</div>
          <div class="reco_details" v-if="show_reco">
            <p>{{ profile.recommendations.title }}</p>
            <ul class="list">
              <li v-for="(item, index) in profile.recommendations.items">{{ item }}</li>
            </ul>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>
<script>
  import { mapGetters } from 'vuex'

  export default {
    components: {
      Detail: () => import('~/components/tab/tab-contents/tab-content-body/Detail'),
      ProgressBar: () => import('~/components/global/ProgressBar'),
      IntroductionDetail: () => import('~/components/tab/tab-contents/tab-content-body/IntroductionDetail'),
    },
    data () {
      return {
        show_reco: false
      }
    },
    computed: {
      ...mapGetters({
        profile: 'data/details/getProfileDetails'
      })
    },
  }
</script>
<style lang="stylus">
  .tab_body
    display: flex
    width: 100%
    .main_details
      width: 100%
      flex: 1 0 calc( 100% - 300px)
      @media(max-width: 1000px)
        flex: 1 0 100%
      .intro_information
        display: flex
        flex-flow: row wrap
        border-bottom: 1.5px solid rgba(0,0,0,0.122)
        .user_image
          width: 100%
          display: flex
          justify-content: center
          align-items: center
          flex: 0 0 130px
          padding: 20px
          border-right: 1.5px solid rgba(0,0,0,0.122)
          .image_wrapper
            border-radius: 100%;
            overflow: hidden;
            box-shadow: 1px 0px 5px 0px rgba(0,0,0,0.1)
            img
              width: 100%
              height: 100%
              object-fit: cover
        .infos
          flex: 1 0 calc(100% - 130px)
          padding: 20px
          font-weight: 400
          color: #505669
          img
            width: 15px
            height: 15px
            margin-right: 5px
          .name_job
            margin-bottom: 15px
            .job_title
              font-size: 15px
              margin-top: 5px
          .extras
            display: flex
            flex-flow: row wrap
            justify-content: space-between
            width: 100%
            max-width: 500px
            margin: 10px auto 0 0
            .item
              display: flex
              align-items: center
              font-size: 14px
              font-weight: 400
          .school
            display: flex
            align-items: center
            font-size: 14px
            font-weight: 400
    .extra_details
      width: 100%
      flex: 0 0 calc(300px - 30px)
      margin-left: 30px
      #video_introduction
        oveflow: hidden
        .title
          padding: 20px
        .vid_thumbnail
          img
            width: 100%
            object-fit: cover
      #profile_completion
        .title
          margin-bottom: 5px
        .success_message
          display: flex
          flex-direction: column
          align-items: center
          .label
            font-size: 18px
            color: #21C55E
            padding: 10px 0 5px
          img
            width: 70px
            padding-bottom: 15px
          .message 
            font-size: 15px
        .recommendation_container
          .reco_title
            font-weight: 300
            color: #505669
            font-size: 14px
          .reco_title
            position: relative
            padding: 10px 0 10px 20px
            cursor: pointer
            &:before
              content: ''
              background: url('/chevron-down-solid.svg')
              background-repeat: no-repeat
              position: absolute
              top: 10px
              left: 0
              padding: 8px
          .reco_details
            padding-left: 10px
            p
              font-weight: 300
              color: #505669
              font-size: 14px
            ul
              padding-top: 10px
              list-style: circle
              padding-left: 20px
              li
                font-size: 14px
                font-weight: 300
                color: #505669
                font-size: 14px
</style>