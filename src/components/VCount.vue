<template>
  <!-- The template doesn't care what the source of the data is as long as it's
  somehwere inside the component's scope-->
  <div class="count">{{ displayCount }}</div>
</template>

<script>
export default {
  props: {
    count: {
      type: Number,
      required: true
    }
  },

  computed: {
    displayCount() {
      // Vue automatically figures out which props/data the computed prop depends on
      // and recalculates it accordingly
      return this.count || "😴";
    }
  }
};
</script>

<style lang="scss" scoped>
.count {
  color: #FFF;
  font-size: 100px;
  font-weight: bold;
  line-height: 1.1;
  margin-bottom: 50px;
  text-align: center;
}
</style>
