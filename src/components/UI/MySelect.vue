<template>
  <select
      class="select-btn"
      @change="changeOption"
  >
    <option
        v-for="option in options"
        :key="option.value"
        :value="option.value"
    >
      {{option.name}}
    </option>
  </select>
</template>

<script>
export default {
  name: "MySelect",
  props: {
    value: {
      type: [String, Number]
    },
    options: {
      type: Array,
      default: () => []
    }
  },
  methods: {
    changeOption(event) {
      this.$emit('input', event.target.value)
    }
  }
}
</script>

<style scoped>
.select-btn {
  height: 36px;
  background: #FFFEFB;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  border-radius: 4px;
  font-weight: 400;
  font-size: 12px;
  line-height: 15px;
  color: black;
}
</style>