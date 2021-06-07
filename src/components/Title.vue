<template>
  <h1>
    <slot/>
  </h1>
</template>

<script>
export default {
  name: "Title"
}
</script>

<style scoped>
h1 {
  padding-top: 60px;
}
</style>