<template>
  <button
    class="button"
    :disabled="disabled"
    @click="handleClick"
  >
    <slot />
  </button>
</template>

<script>
export default {
  name: 'BaseButton',
  props: {
    disabled: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    handleClick () {
      this.$emit('click')
    }
  }
}
</script>
<style lang="scss" scoped>
  .button {
    color: var(--primary-color);
    font-size: 2rem;
    padding: 15px 45px;
    border: none;
    border-radius: 50px;
    cursor: pointer;
    background-color: white;
    &:hover {
      background-color: #dddddd;
    }
    &:active {
      background-color: white;
    }
  }

  .primary {
    color: white;
    background-color: var(--primary-color);
    &:hover {
      background-color: #0a82f1;
    }
    &:active {
      background-color: var(--primary-color);
    }
  }
</style>
