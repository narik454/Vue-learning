<template>
<input
    placeholder="Поиск"
    @input="$emit('update:input', value)"
>
</template>

<script>
export default {
  name: "MySearch",
  props: {
    value: String
  }
}
</script>

<style scoped>

</style>