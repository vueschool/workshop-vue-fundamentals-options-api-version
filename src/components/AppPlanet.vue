<script>
export default {
  emits: ["visited"],
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
      {{ name }} Visted
      <input
        type="number"
        :value="visits"
        :style="{ display: 'inline', width: '30px' }"
        @input="$emit('visited', $event.target.value)"
        min="0"
        max="9"
      />
      time(s)
      <button @click="$emit('visited', visits + 1)">Visit</button>
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
