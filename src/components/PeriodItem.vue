<template>
  <div v-bind:class="'defaultPeriodeContainerStyle flex between-h '+periodeContainerStyle">
      <div class="left-text">
        <DefaultText v-bind:text="periodTextProp" v-bind:textStyle="periodStyleProp" />
        <DefaultText text="Current Period" textStyle="current-period-txt-style initial-display" />
      </div>

      <div class="flex">
        <DefaultText text="12:09 - 12:09 pm" textStyle="begin-end-txt-style green-text margin-auto m-r32" />
        <TimeText v-bind:hour="hh" v-bind:minutes="mm" v-bind:seconds="ss" textStyle="time-style margin-auto" secondesStyle="weight-300 robotoFontLight"/>
      </div>
  </div>
</template>

<script>
  import DefaultText from './DefaultText.vue'
  import TimeText from './TimeText.vue'

export default {
    name: 'PeriodItem',
    components: {
      DefaultText,
      TimeText,
    },
    props: {

      // TimeText props
      hh: {
        type: String,
        default: "00"
      },
      mm: {
        type: String,
        default: "00"
      },
      ss: {
        type: String,
        default: "00"
      },
      secondesStyle: {
        type: String,
        default: "default-text-style robotoFontLight"
      },

      // periode props

      periodTextProp: {
        type: String,
        default: "default-text-style"
      },
      
      periodStyleProp: {
        type: String,
        default: "default-text-style"
      },
      
      periodNumberProp: {
        type: String,
        default: "default-text-style"
      },



      periodeContainerStyle: {
        type: String,
        default: "defaultPeriodeContainerStyle"
      },
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
  .defaultPeriodeContainerStyle {
      padding: 23px 64px;
      border-top: 1px solid $light-gray-color;
      border-bottom: 1px solid $light-gray-color;
  }

   .period-number-txt-style {
    color: $gray-color-level-4;
    font-family: $robotoFont;
    font-style: normal;
    font-weight: 900;
    font-size: 16px;
    line-height: 19px;
  }



</style>
