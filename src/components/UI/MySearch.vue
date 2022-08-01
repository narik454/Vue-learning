<template>
<input
    placeholder="Поиск"
    @input="search"
>
</template>

<script>
export default {
  name: "MySearch",
  props: {
    value: String
  },
  methods: {
    search(e) {
      this.$emit('input', e.target.value)
    }
  }
}
</script>

<style scoped>

</style>