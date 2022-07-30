<template>
  <select
      class="select-btn"
      @change="changeOption"
      :value ="modelValue"
  >
    <option value="">По умолчанию</option>
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
  data(){
    return {
      modelValue: this.value
    }
  },
  props: {
    value: {
      type: String
    },
    options: {
      type: Array,
      default: () => []
    }
  },
  methods: {
    changeOption(event) {
      this.$emit('update:value', event.target.value)
    }
  }
}
</script>

<style scoped>

</style>