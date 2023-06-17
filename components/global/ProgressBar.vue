<template>
  <div 
    :class="`progress ${(percentage <= 33.33) ? 'low' : (percentage <= 99) ? 'mid' : 'success'}`"
  >
    <div class="line">
      <div class="line_prog"></div>
    </div>
    <span 
      class="percentage" 
      :style="`${(!is_label_below) ? 'top: -4px; right: -37px;': ''}`"
    >
      {{percentage}}%
    </span>
  </div>
</template>
<script>
  export default {
    props: {
      percentage: {
        type: Number,
        default: 0,
        required: true
      },
      is_label_below: {
        type: Boolean,
        default: false,
        required: false
      },
    }
  }
</script>
<style lang="stylus">
.progress
  position: relative
  .line
    width: 100%
    height: 10px
    padding: 5px
    overflow: hidden
    border-radius: 25px
    background: #E5E8EE
    position: relative
    .line_prog
      position: absolute
      top: 0
      left: 0
      right: 0
      bottom: 0
      width: 100%
      height: 100%
  .percentage 
    font-size: 13px
    font-weigh: 400
    position: absolute
    top: -20px
    right: 0
  &.low
    .line_prog
      background: #FF6161
      width: 20%
    .percentage
      color: #FF6161
  &.mid
    .line_prog
      background: #FFA953
      width: 50%
    .percentage
      color: #FFA953
  &.success
    .line_prog
      background: #21C55E
      width: 100%
    .percentage
      color: #21C55E
</style>
