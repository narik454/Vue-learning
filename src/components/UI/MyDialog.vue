<template>
  <div class="dialog" v-if="value" @click="hideDialog">
    <div class="dialog__content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "MyDialog",
  props: {
    value: {
      type: [Boolean, Object],
      default: false
    }
  },
  methods: {
    hideDialog() {
      this.$emit('input', false);
    }
  }
}
</script>

<style scoped>

.dialog {
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  background: rgba(0,0,0, 0.5);
  position: fixed;
  display: flex;
  z-index: 999;
}

.dialog__content {
  margin: auto;
  background: white;
  border-radius: 15px;
  padding: 20px;
}

</style>