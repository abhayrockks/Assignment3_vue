<template>
  <div class="timer">
    <p>{{time}}{{display}}</p>
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
  },

  computed: {
    display: function() {
      if (this.tflag) {
        return this.toggleTimer();
      } else {
        return this.reset();
      }
    }
  }
};
</script>

<style scoped>
</style>