<template>
  <div>
    <v-counter v-model="count" :goal="goal" @done="showHelloWorld"/>
    <div class="hello-world" v-if="goalMet">Hello Vuerld 🙋🏻‍♀️</div>
  </div>
</template>

<script>
import VCounter from "@/components/VCounter.vue";

export default {
  components: {
    VCounter
  },

  data() {
    return {
      count: 0,
      goal: 10,
      goalMet: false
    };
  },

  methods: {
    showHelloWorld() {
      this.goalMet = true;
    }
  }
};
</script>

<style lang="css" scoped>
.hello-world {
  color: #FFF;
  font-size: 60px;
  line-height: 1.1;
  margin-top: 50px;
}
</style>

