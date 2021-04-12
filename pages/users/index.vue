<template>
  <section>
    <h1>{{ pageTitle }}</h1>
    <ol>
      <li v-for="user in users" :key="user.id">
        <a href="#" @click.prevent="goTo(user)">{{ user.name }} ( {{user.email}} )</a>
        
      </li>
    </ol>
  </section>
</template>
<script>
export default {
  asyncData({ $axios, error }) {
    return $axios
      .get("https://jsonplaceholder.typicode.com/users")
      .then((params) => {
        const users=params.data;
        return { users };
      })
      .catch(err => {
        error(err);
      });
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
