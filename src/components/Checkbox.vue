<template>
  <label>
    <input
        type="checkbox"
        :checked="value"
        @input="$emit('input', $event.target.checked)"
    >
    <span>{{ label }}</span>
  </label>
</template>

<script>
export default {
  name: "Checkbox",
  props: {
    label: String,
    value: String
  },
}
</script>

<style scoped>
input {
  margin: 10px;
}
</style>