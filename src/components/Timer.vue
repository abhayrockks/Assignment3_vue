<template>
  <div class="timer">
    <p v-if="tflag ? 'toggleTimer':'reset'">{{time}}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      time: 0,
      interval: null
    };
  },
  props: {
    tflag: Boolean
  },

  methods: {
    toggleTimer() {
      this.interval = setInterval(this.incrementTime, 1000);
    },
    incrementTime() {
      this.time = parseInt(this.time) + 1;
    },
    reset() {
      clearInterval(this.interval);
    }
  }
};
</script>

<style scoped>
</style>