<template>
  <button
    :class="['button', type]"
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
    disabled: Boolean,
    type: {
      type: String,
      default: 'button'
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
  }

  .primary {
    color: white;
    background-color: var(--primary-color);
    &:hover {
      background-color: #0a82f1;
    }
  }
</style>
