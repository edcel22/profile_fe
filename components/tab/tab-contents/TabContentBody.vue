<template>
  <div class="tab_body">
    <div class="main_details box">
      <div class="intro_information">
        <div class="user_image">
          <div class="image_wrapper">
            <img src="/user_image.png" alt="" />
          </div>
        </div>
        <div class="infos">
          <div class="name_job">
            <h2 class="name">Edcel Estadola</h2>
            <p class="job_title">Full Stack Developer</p>
          </div>
          <div class="school">
            <img src="/graduation-cap-solid.svg" alt="">
            <span>Bachelor of Science in Information Technology</span>
          </div>
          <div class="extras">
            <div class="item">
              <img src="/briefcase-solid.svg" alt="">
              <span>12 years</span>
            </div>
            <div class="item">
              <img src="/calendar-regular.svg" alt="">
              <span>Immediately</span>
            </div>
            <div class="item">
              <img src="/peso-sign-solid.svg" alt="">
              <span>Php 00, 000</span>
            </div>
          </div>
        </div>
      </div>
      <div class="other_details">
        <!-- General Details -->
        <Detail :detail="general_details" />
        <!-- Professional Status -->
        <Detail :detail="professional_status" />
        <!-- Preference -->
        <Detail :detail="preferences" />
      </div>
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
        <div class="progress success">
          <div class="line">
            <div class="line_prog"></div>
          </div>
          <span class="percentage">100%</span>
        </div>
        <div class="success_message">
          <h2 class="label">Well done, Reyven!</h2>
          <img src="/success_icon.png" alt="">
          <div class="message">
            <p>You have one of the strongest professional profile in our talen pool.</p>
            <p>Expect progress on your applciation at any time soon.</p>
          </div>
        </div>
      </section>

      <section id="profile_completion" class="box padding">
        <div class="title">Profile Completion</div>
        <div class="progress mid">
          <div class="line">
            <div class="line_prog"></div>
          </div>
          <span class="percentage">50%</span>
        </div>
        <div class="recommendation_container">
          <div class="reco_title" @click="show_reco ^= true">Show Recommendation</div>
          <div class="reco_details" v-if="show_reco">
            <p>Fill-up the following items to strengthen your profile. This can help us in matching your profile and increase your chances of landing into your desired role.</p>
            <ul class="list">
              <li>Pre Employment Leaves</li>
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
    },
    data () {
      return {
        show_reco: false
      }
    },
    computed: {
      ...mapGetters({
        general_details: 'data/details/getGeneralDetails',
        professional_status: 'data/details/getProfessionalStatus',
        preferences: 'data/details/getPreferences'
      })
    },
  }
</script>
<style lang="stylus">
  .tab_body
    display: flex
    flex-flow: row wrap
    width: 100%
    .main_details
      width: 100%
      flex: 1 0 calc( 100% - 300px)
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
      .other_details
        display: flex
        flex-direction: column
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