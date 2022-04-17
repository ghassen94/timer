<template>
  <div class="flex between-h m-b97">
    <div>
      <DefaultText text="Today, 08 Oct" textStyle="today-txt-style margin-auto" />
    </div>
    <div class="flex">
      <DefaultButton btn-style="m-r13 red-text red-border" v-bind:withIcon="true" btn-text="Stop" :icon-src="require('@/assets/images/play.svg')" />
      <DefaultButton v-bind:action="start" btn-style="m-r32 green-text green-border" v-bind:withIcon="true" btn-text="Start new" :icon-src="require('@/assets/images/clock.svg')" />
      <TimeText hour="01" minutes="24" seconds="54" textStyle="time-style green-text margin-auto" secondesStyle="weight-300 robotoFontLight"/>
    </div>
  </div>

  <PeriodItem text="12:09 - 12:09 pm" textStyle="begin-end-txt-style" />
  <PeriodItem text="12:09 - 12:09 pm" textStyle="begin-end-txt-style" />
  <PeriodItem text="12:09 - 12:09 pm" textStyle="begin-end-txt-style" />
  <PeriodItem text="12:09 - 12:09 pm" textStyle="begin-end-txt-style" />

  <!-- ************************************************************************ -->
  <!-- <hr class="m-t20"/>
  <DefaultButton v-bind:withIcon="true" btn-text="Button text" :icon-src="require('@/assets/images/clock.svg')" />
  <DefaultText text="Today, 08 Oct" textStyle="today-txt-style" />
  <DefaultText text="Period 3" textStyle="period-number-txt-style" />
  <DefaultText text="Current Period" textStyle="current-period-txt-style" />
  <DefaultText text="12:09 - 12:09 pm" textStyle="begin-end-txt-style" />
  <DefaultText text="12:09 - 12:09 pm" textStyle="begin-end-txt-style green-text" />
  <TimeText hour="01" minutes="24" seconds="54" textStyle="time-style" secondesStyle="weight-300 robotoFontLight"/>
  <TimeText hour="01" minutes="24" seconds="54" textStyle="time-style green-text" secondesStyle="weight-300 robotoFontLight"/>
  <DefaultText text="Total" textStyle="total-time-txt-style" /> -->

</template>

<script>
  import DefaultButton from './components/DefaultButton.vue'
  import DefaultText from './components/DefaultText.vue'
  import TimeText from './components/TimeText.vue'
  import PeriodItem from './components/PeriodItem.vue'
  export default {
    name: 'App',
    components: {
      DefaultButton,
      DefaultText,
      TimeText,
      PeriodItem
    },
    data() {
        return {
          h:0,
          min:0,
          sec:0,
          isRunning: false,
          minutes:0,
          secondes:0,
          time:0,
          timer:null,
        }
    },
    methods: {
      start () {
        this.isRunning = true
        if (!this.timer) {
          this.timer = setInterval( () => {
            this.sec++
            console.log('time is : ', this.time)
          }, 1000 )
        }
      },
      stop () {
        this.isRunning = false
        //  clearInterval(this.timer)
        this.timer = null
      }
    },
    created: () => {
      console.log("app created")
    }
  }
</script>

<style lang="scss">
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    padding: 10% 20%;
  }

  .m-t20 {
    margin-top: 20px;
  }

  .margin-auto {
    margin: auto;
  }

  .m-b97 {
    margin-bottom: 97px !important;
  }

  .m-r13 {
    margin-right: 13px !important;
  }
  
  .m-r32 {
    margin-right: 32px !important;
  }

  .flex  {
    display: flex;
  }

  .initial-display {
    display: initial;
  }

  .between-h {
    justify-content: space-between;
  }

  .weight-300 {
    font-weight: 300 !important;
  }

  .robotoFontLight {
    font-family: $robotoFontLight !important;
  }

  .red-text {
    color: $red-color !important;
  }

  .red-border {
    border-color: $red-color !important;
  }

  .green-text {
    color: $green-color !important;
  }

  .left-text {
    text-align: left;
  }

  .right-text {
    text-align: right;
  }

  .green-border {
    border-color: $green-color !important;
  }

  .no-bottom-border {
    border-bottom: none;
  }

  .today-txt-style {
    color: $gray-color-level-5;
    font-family: $robotoFont;
    font-style: normal;
    font-weight: 900;
    font-size: 30px;
    line-height: 35px;
  }

  .period-number-txt-style {
    color: $gray-color-level-4;
    font-family: $robotoFont;
    font-style: normal;
    font-weight: 900;
    font-size: 16px;
    line-height: 19px;
  }

  .current-period-txt-style {
    color: $gray-color-level-1;
    font-family: $robotoFont;
    font-style: normal;
    font-weight: 900;
    font-size: 16px;
    line-height: 19px;
  }

  .begin-end-txt-style {
    color: $gray-color-level-3;
    font-family: $robotoFontMeduim;
    font-style: normal;
    font-weight: 900;
    font-size: 14px;
    line-height: 16px;
  }

  .time-style {
    color: $gray-color-level-5;
    font-family: $robotoFontMeduim;
    font-style: normal;
    font-weight: 900;
    font-size: 25px;
    line-height: 29px;
  }

  .total-time-txt-style {
    color: $gray-color-level-2;
    font-family: $robotoFont;
    font-style: normal;
    font-weight: 900;
    font-size: 25px;
    line-height: 29px;
  }

</style>
