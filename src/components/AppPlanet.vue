<script>
export default {
  props: {
    name: { type: String, required: true },
    visits: { type: Number, required: true },
  },
  computed: {
    showIcon() {
      return this.visits > 0;
    },
  },
};
</script>
<template>
  <li>
    <span>
      <strong>Planet:</strong>
      {{ name }} Visted {{ visits }} time(s)
    </span>
    <span v-if="showIcon">🚀</span>
  </li>
</template>

<style scoped>
li {
  display: flex;
  justify-content: space-between;
}
</style>
