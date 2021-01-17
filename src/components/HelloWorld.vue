<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>{{ count }}</h2>

    <button v-on:click="count++">Increment</button>
    <button v-on:click="decrementToMaxOfZero()">Decrement</button>
    <button v-on:click="count = 0">Reset</button>
    <ul id="example-2">
      <li v-for="(todo, idx) in todos" :key="todo.text" v-on:click="removeTodo(idx)">
        {{ idx + 1 }} - {{ todo.text }}
      </li>
    </ul>
    <input v-model="message" placeholder="edit me" />
    <p>Message is: {{ message }}</p>
    <button v-on:click="addTodo">Add Todo</button>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      count: 1,
      message: "",
      todos: [
        { text: "Hello World" },
        { text: "Hello Loi" },
        { text: "Hello Tran" },
      ],
    };
  },

  methods: {
    decrementToMaxOfZero() {
      if (this.count > 0) {
        this.count--;
      } else {
        this.count;
      }
    },
    addTodo() {
      this.todos.push({
        text: this.message,
      });
      this.message = "";
    },
    removeTodo(chosenIdx) {
      this.todos = this.todos.filter((_, currentIdx) => currentIdx !== chosenIdx)
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
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
