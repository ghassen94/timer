<template>
  <p v-bind:class="textStyle">
    {{ text }}
  </p>
</template>

<script>
  export default {
    name: 'DefaultText',
    props: {
      text: {
        type: String,
        default: "default-text"
      },
      textStyle: {
        type: String,
        default: "default-text-style"
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
