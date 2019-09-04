<template>
  <button
    :class="[type ? 'button-'+type : '']"
    @click="handleClick"
  >
    <span v-if="$slots.default">
      <slot></slot>
    </span>
  </button>
</template>

<script type="ts">
export default {
  name: 'Button',
  props: {
    type: {
      type: String,
      default: 'primary'
    }
  },
  methods: {
    handleClick(event) {
      this.$emit('click', event)
    }
  }
}
</script>

<style scoped lang="scss">
@import "@/assets/scss/variable.scss";

.button-primary {
  background-color: $button-primary-bg-color;
}
button {
  width: 120px;
  height: 30px;
  outline: none;
  border-radius: 4px;
  border: none;
  color: $button-global-font-color;
}

.button-primary:active {
  background-color: $button-primary-active-bg-color;
  color: #dddddd;
}
</style>
