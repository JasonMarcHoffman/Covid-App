<template>
  <div>
    <h2>{{ title }}</h2>
  </div>
</template>

<script>
export default {
  props: {
    title: {type: String, required: true}
  }
}
</script>

<style scoped>
  div {
    position: relative;
    top: 0;
    left: 0;
    background-color: rgb(2, 62, 129);
    color: white;
    width: 100vw;
  }

  h2 {
    text-align: center;
    padding: 1rem;
    color: white;
  }
</style>