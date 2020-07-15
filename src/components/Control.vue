<template>
  <div class="control">
    <timer :tflag="cflag" />
    <button @click="cflag = true">{{label1}}</button>
    <button @click="cflag = false">{{label2}}</button>
  </div>
</template>

<script>
import timer from "./Timer.vue";
export default {
  components: {
    timer
  },
  data() {
    return {
      label1: "Start",
      label2: "Stop",
      cflag: false
    };
  }
};
</script>

<style scoped>
</style>