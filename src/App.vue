<script>
import GithubUserCard from "./components/GithubUserCard.vue";

export default {
  components: { GithubUserCard },
  data() {
    return {
      usernames: ["yyx990803", "antfu", "danielkellyio"],
    };
  },
};
</script>

<template>
  <h2>Github Users</h2>
  <GithubUserCard
    v-for="username in usernames"
    :key="username"
    :username="username"
  />
</template>
