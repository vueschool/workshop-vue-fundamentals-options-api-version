<script>
import AppPlanet from "./components/AppPlanet.vue";
export default {
  components: { AppPlanet },
  data() {
    return {
      planets: [
        { name: "Mercury", visits: 2 },
        { name: "Venus", visits: 0 },
        { name: "Jupiter", visits: 5 },
        { name: "Mars", visits: 1 },
      ],
    };
  },
};
</script>

<template>
  <ul>
    <AppPlanet
      v-for="planet in planets"
      :key="planet.name"
      :name="planet.name"
      :visits="planet.visits"
    ></AppPlanet>
  </ul>
</template>
