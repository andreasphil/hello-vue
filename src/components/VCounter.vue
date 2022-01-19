<template>
  <div class="counter">
    <v-count :count="localValue"/>
    <v-button label="Increment" :disabled="!canIncrement" @click="++localValue" primary/>
    <v-button label="Decrement" :disabled="!canDecrement" @click="--localValue"/>
  </div>
</template>

<script>
import VButton from '@/components/VButton.vue'
import VCount from '@/components/VCount.vue'

export default {
  components: {
    VButton,
    VCount
  },

  props: {
    value: {
      type: Number,
      default: 0
    },
    goal: {
      type: Number,
      default: -1
    }
  },

  computed: {
    localValue: {
      get () {
        return this.value
      },
      set (value) {
        this.$emit('input', value)
      }
    },

    canDecrement () {
      return this.localValue > 0
    },

    canIncrement () {
      return this.goal > 0 && this.localValue < this.goal
    }
  },

  watch: {
    value: function (val) {
      val === this.goal && this.$emit('done')
    }
  }
}
</script>

<style lang="css" scoped>
.counter {
  padding: 50px;
  background-color: rgba(255, 255, 255, 0.075);
}
</style>
