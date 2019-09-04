<template>
  <div class="input-wrapper">
    <input
      v-bind="$attrs"
      :inputValue="inputValue"
      v-on="inputListener"
    >
  </div>
</template>

<script type="ts">
export default {
  name: 'Input',
  props: {
    inputValue: {
      type: String,
      default: ''
    }
  },
  computed: {
    inputListener() {
      const vm = this
      return Object.assign({}, this.$listeners, {
        input: (event) => {
          vm.$emit('input', event.target.value)
        }
      })
    }
  }
}
</script>

<style scoped lang="scss">
.input-wrapper {
  display: inline-block;
  input {
    width: 200px;
    height: 30px;
    border-left: none;
    border-right: none;
    border-top: none;
    border-bottom: 1px solid #aaaaaa;
    padding-left: 6px;
    outline: none;
    -webkit-appearance: none;
    font-size: 14px;
    &:focus {
      border-bottom: 1px solid #000000;
    }
  }
}
</style>
