<template>
  <button
<<<<<<< HEAD
    :class="['button', internalType]"
=======
    class="button"
>>>>>>> main
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
<<<<<<< HEAD
    disabled: Boolean
  },
  computed: {
    internalType () {
      return this.type
=======
    disabled: {
      type: Boolean,
      default: false
>>>>>>> main
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
<<<<<<< HEAD
=======

>>>>>>> main
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
