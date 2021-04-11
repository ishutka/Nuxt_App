<template>
  <section>
    <h1>{{ pageTitle }}</h1>
    <ol>
      <li v-for="user in users" :key="user">
        <a href="#" @click.prevent="goTo(user)">User {{ user }}</a>
      </li>
    </ol>
  </section>
</template>
<script>
export default {
  asyncData() {
    return new Promise(resolve => {
      setTimeout(() => {
        resolve({ users: [1, 2, 3, 4, 5] });
      },2000);
    });
  },
  data() {
    return {
      pageTitle: "Users Page"
    };
  },
  methods: {
    goTo(u) {
      this.$router.push("/users/" + u);
    }
  }
};
</script>
