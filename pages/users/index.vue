<template>
  <section>
    <h1>Users Page</h1>
    <ol>
      <li v-for="user in users" :key="user">
          <a href="#" @click.prevent="goTo(user)">User {{ user }}</a>
          </li>
    </ol>
  </section>
</template>
<script>
export default {
  data() {
    return {
      users: [1, 2, 3, 4, 5]
    };
  },
methods:{
    goTo(u){
        this.$router.push('/users/'+ u);
    }
}
};
</script>
