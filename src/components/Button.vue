<template>
  <button class="Button" @click="$emit('click')">
    <slot/>
  </button>
</template>

<script>
export default {
  name: "Button"
}
</script>

<style scoped>
.Button {
  margin-top: 20px;
  width: 200px;
  height: 30px;
}
</style>