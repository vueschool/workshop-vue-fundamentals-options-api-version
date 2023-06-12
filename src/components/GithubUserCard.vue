<script>
export default {
  props: {
    username: { type: String, required: true },
  },
  data() {
    return {
      user: null,
    };
  },
  async created() {
    const res = await fetch(`https://api.github.com/users/${this.username}`);
    this.user = await res.json();
  },
};
</script>

<template>
  <div class="card" v-if="user">
    <img class="card-img" :src="user.avatar_url" :alt="user.name" />
    <div class="card-info">
      <h2 class="card-name">{{ user.name }}</h2>
      <p class="card-followers">
        Number of Followers: {{ user.followers.toLocaleString() }}
      </p>
    </div>
  </div>
</template>

<style scoped>
.card {
  padding: 10px;
  box-shadow: 0 0 4px rgba(0, 0, 0, 0.2);
  border-radius: 5px;
  display: flex;
  margin-bottom: 10px;
}

.card-img {
  width: 100px;
}
.card-info {
  padding: 10px;
}
.card-name {
  padding: 0;
  margin: 0;
  font-size: 1rem;
}

.card-followers {
  font-size: 0.8rem;
  margin: 0;
}
</style>
