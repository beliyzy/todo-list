<template>
  <label>
    <span>{{ label }}</span>
    <input
        :value="value"
        @input="$emit('input', $event.target.value.trim())"
    >
  </label>
</template>

<script>
export default {
  name: "Input",
  props: {
    label: String,
    value: String,
  }
}
</script>

<style scoped>
input {
  margin-top: 40px;
  width: 300px;
  height: 30px;
}
span {
  margin-right: 5px;
}
</style>
