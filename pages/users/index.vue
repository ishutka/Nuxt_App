<template>
  <section>
    <h1>{{ pageTitle }}</h1>
    <ol>
      <li v-for="user in users" :key="user.id">
        <a href="#" @click.prevent="goTo(user)"
          >{{ user.name }} ( {{ user.email }} )</a
        >
      </li>
    </ol>
  </section>
</template>
<script>
export default {
  async asyncData({ store, error }) {
    
    try {
      const users = await store.dispatch("users/fetchUsers");
      return { users };
    } catch (e) {
      error(e);
    }
  },
  data() {
    return {
      pageTitle: "Users Page"
    };
  },
  methods: {
    goTo(u) {
      this.$router.push("/users/" + u.id);
    }
  }
};
</script>
