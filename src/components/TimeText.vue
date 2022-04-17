<template>
  <p v-bind:class="textStyle">
    {{ hour }}:{{ minutes }}:<span v-bind:class="secondesStyle">{{ seconds }}</span>
  </p>
</template>

<script>
  export default {
    name: 'TimeText',
    props: {
      hour: {
        type: Number,
        default: 0
      },
      minutes: {
        type: Number,
        default: 0
      },
      seconds: {
        type: Number,
        default: 0
      },
      textStyle: {
        type: String,
        default: "default-text-style"
      },
      secondesStyle: {
        type: String,
        default: "default-text-style robotoFontLight"
      },
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
  .default-text-style {
    color: $black-color;
    font-family: $robotoFont;
    font-size: 14px;
  }



</style>
