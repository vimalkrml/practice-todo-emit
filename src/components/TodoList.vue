<template>
  <div>
    <h1>Todo</h1>
    <form @submit.prevent="taskAdd">
      <input v-model="name" type="text" />
      {{ name }}
      <button>ADD</button>
    </form>

    <div class="tasks" v-for="task in tasks" :key="task.id">
      <h1>{{ task.name }}</h1>
      <button @click="taskDelete(task.id)">Delete</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tasks: [],
      name: "",
    };
  },

  methods: {
    async taskShow() {
      await fetch("http://localhost:3000/posts")
        .then((res) => res.json())
        .then((json) => {
          this.tasks = json;
          console.log(json);
        });
    },
    async taskAdd() {
      const requestOptions = {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({
          id: Math.random(),
          name: this.name,
        }),
      };
      await fetch("http://localhost:3000/posts", requestOptions).then((res) =>
        res.json()
      );
      this.name = "";
      this.taskShow();
    },
    async taskDelete(id) {
      console.log(id);
      await fetch("http://localhost:3000/posts/" + id, {
        method: "DELETE",
      });
      this.taskShow();
    },
  },
  created() {
    this.taskShow();
  },
};
</script>

<style scoped>
.tasks {
  display: flex;
  justify-content: space-around;
  gap: 5rem;
  margin-bottom: 2rem;
}
</style>
