<template>
  <div class="home">
    <my-button @change="(e) => (this.name = e)"></my-button>
    <h1>{{ name }}</h1>
    <button @click="a++">Add to A</button>
    <button @click="b--">Sub to B</button>
    <p>{{ c }} + {{ a }} = {{ addToA }}</p>
    <p>{{ c }} - {{ b }} = {{ addToB }}</p>
    <todo-list class="todo" />
  </div>
</template>
<script>
import MyButton from "./MyButton.vue";
import TodoList from "./TodoList.vue";
export default {
  components: { MyButton, TodoList },
  data() {
    return {
      name: "Vimal",
      a: 1,
      b: 10,
      c: 40,
    };
  },
  methods: {
    // addToA() {
    //   console.log("hii");
    //   return this.c + this.a;
    // },
    // addToB() {
    //   console.log("hii");
    //   return this.c + this.b;
    // },
  },
  computed: {
    addToA() {
      console.log("hii");
      return this.c + this.a;
    },
    addToB() {
      console.log("hii");
      return this.c - this.b;
    },
  },
};
</script>
<style scoped>
.todo {
  margin-top: 2rem;
  background-color: bisque;
  padding: 5rem;
}
</style>
