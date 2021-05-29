<template>
  <div class="hello">
    <h1>Hello World!</h1>
  </div>
</template>

<script>
export default {
  name: "TestMount",
  data() {
    return {
      count: 0
    }
  },
  beforeMount() {
    console.log('beforeMount')
  },
  mounted() {
    this.interval = setInterval(() => {
      console.log('Hi', this.count)
      this.count = this.count + 1
    }, 1000)
    console.log("Mounted");
  },
  beforeDestroy() {
    clearInterval(this.interval)
    console.log('beforeDestroy')
  },
};
</script>

<style scoped>
</style>
