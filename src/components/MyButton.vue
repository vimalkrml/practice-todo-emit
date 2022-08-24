<template>
  <div>
    <button @click="$emit('change', name)">change</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "Gokul",
    };
  },
};
</script>

<style></style>
