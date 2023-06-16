<template>
  <div class="top_navigation">
    <div class="wrapper">
      <div class="left">
        <div class="logo">
          <img src="/goteam-logo-dark.png" alt="">
        </div>
        <div class="navlinks">
          <ul>
            <li>
              <nuxt-link to="">Careers</nuxt-link>
            </li>
            <li>
              <nuxt-link to="">Find your role</nuxt-link>
            </li>
          </ul>
        </div>
      </div>
      <div class="middle">
        <div class="search_input">
          <input type="text" placeholder="Type for job title or role" class="input round">
          <div class="primary_button round">
            <img src="" alt="">
            <span>Search</span>
          </div>
        </div>
      </div>
      <div class="right">
        <div class="account">
          <img src="" alt="" class="profile_img">
          <div class="info">
            <p class="name">Edcel Estadola</p>
            <p class="email">edcel.estadola.dev@gmail.com</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<style lang="stylus">
  .top_navigation
    .wrapper
      display: flex
      align-items: center
      justify-content: space-between
      background-color: #fff
      border-radius: 5px
      box-shadow: 0 0 30px rgba(0,0,0,.1)
      position: fixed
      right: 0
      top: 0
      transition: .3s ease-in-out
      width: 100%
      z-index: 2
      padding: 20px 40px
      .left,
      .right,
      .middle
        display: flex
        align-items: center
      .left
        .logo
          width: 100px
          img
            width: 100%
        .navlinks
          ul
            display: flex
            li
              padding: 5px
              margin: 0 10px
              a
                font-weight: 300
      .right
        display: flex
        .account
          display: flex
          align-items: center
          .info
            display: flex
            flex-direction: column
            align-items: flex-end
            p
              &.name
                font-weight: 600px
            .email
              font-size: 12px
              color: #6881F8
      .search_input
        display: flex
        justify-content: flex-end
        border-radius: 20px
        border: 0.5px solid #5056694d
        overflow: hidden
        width: 300px
        input
          flex-grow: 1
          padding: 0 20px
          border: none
</style>