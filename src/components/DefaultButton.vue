<template>
<button >
<i class="bi-alarm"></i>

  {{ btnText }}
  <svg class="bi bi-volume-mute-fill" aria-hidden="true" >
  </svg>
</button>
</template>

<script>
  import playIcon from './logo.svg';
  import clockIcon from './logo.svg';

  export default {
    name: 'DefaultButton',
    props: {
      btnStyle: String,
      btnTextStyle: String,
      btnText: String,
      action: Function,
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
