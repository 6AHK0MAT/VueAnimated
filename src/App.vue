<template>
  <div class="container text-center pt-5">
    <button class="btn btn-primary mb-5" @click="show = !show">Toggle</button>

    <!--<transition-->
      <!--name="ma"-->
      <!--:duration="{enter: 1500, leave: 200}"-->
      <!--appear-->
    <!--&gt;-->
      <!--<p v-if="show">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Iure, minus?</p>-->
    <!--</transition>-->
    <!--<transition-->
      <!--enter-active-class="animated wobble"-->
      <!--leave-active-class="animated shake"-->
    <!--&gt;-->
      <!--<p v-if="show">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Error, obcaecati.</p>-->
    <!--</transition>-->

    <transition name="ma" mode="in-out">
        <div class="alert alert-success" v-if="show" key="success">Success</div>
        <div class="alert alert-danger" v-else key="danger">Danger</div>
    </transition>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        show: true
      }
    }
  }
</script>

<style>

  .ma-enter {
    opacity: 0;
  }
  .ma-enter-active {
    transition: opacity 1s;
  }
  .ma-enter-to {}

  .ma-leave {}
  .ma-leave-active {
    animation: 1s ma-slide forwards;
    transition: opacity 1s;
  }
  .ma-leave-to {
    opacity: 0;
  }

  @keyframes ma-slide {
    from {
      transform: translateX(0px);
    }
    to {
      transform: translateX(-100px);
    }
  }


</style>
