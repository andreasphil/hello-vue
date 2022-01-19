<template>
  <!-- Basically just a wrapper around the native button element to apply some
  styling-->
  <button
    class="button"
    :class="{ primary, disabled }"
    :disabled="disabled"
    @click="onClick"
  >{{ label }}</button>
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      required: true
    },
    primary: {
      type: Boolean,
      default: false
    },
    disabled: {
      type: Boolean,
      default: false
    }
  },

  methods: {
    onClick () {
      this.$emit('click')
    }
  }
}
</script>

<style lang="css" scoped>
.button {
  background-color: transparent;
  border: 2px solid #009DE0;
  color: #FFF;
  font-family: "Interstate", -apple-system, Helvetica, Arial, sans-serif;
  font-size: 24px;
  font-weight: bold;
  min-width: 200px;
  padding: 10px 20px;
  text-align: center;
}

button + button {
  margin-left: 20px;
}

button.primary {
  background-color: #009DE0;
  color: #FFF;
  cursor: pointer;
}

button.primary.disabled {
  color: #FFF;
  background-color: #D6267F;
}

button.disabled {
  border-color: #D6267F;
  color: #D6267F;
  cursor: not-allowed;
}

</style>
