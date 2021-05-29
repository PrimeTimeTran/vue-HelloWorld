<template>
  <div class="hello">
    <h2>{{ count }}</h2>
    <TestMount v-if="count % 2 === 0" />
    <button v-on:click="count++">Increment</button>
    <button v-on:click="decToZero()">Decrement</button>
  </div>
</template>

<script>
import TestMount from "./TestMount.vue";

export default {
  name: "HelloWorld",
  components: {
    TestMount,
  },
  props: {
    property: String,
  },

  data() {
    return {
      count: 1,
    };
  },

  methods: {
    decToZero() {
      this.count > 0 && this.count--;
    },
  },
};
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  margin: 0 10px;
}
a {
  color: #42b983;
}
#example-2 {
  flex-direction: column;
}
</style>
