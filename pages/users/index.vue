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
  async fetch({ store,error }) {
    try {
      if (store.getters["users/users"].length === 0)
        await store.dispatch("users/fetchUsers");
    } catch (e) {
      error(e);
    }
  },
  data() {
    return {
      pageTitle: "Users Page"
    };
  },
  computed: {
    users() {
      return this.$store.getters["users/users"];
    }
  },
  methods: {
    goTo(u) {
      this.$router.push("/users/" + u.id);
    }
  }
};
</script>
