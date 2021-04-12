<template>
  <div>
    <h1>{{ user.name }} id: {{ user.id }}</h1>
    <hr />
    <p>{{ user.email }}</p>
  </div>
</template>
<script>
export default {
  validate({ params }) {
    console.log(params);
    return /^\d+$/.test(params.id);
  },
  async asyncData({ params, error, store }) {
    try {
      const user = await store.dispatch("users/fetchUserById", params.id);
      return { user };
    } catch (e) {
      error(e);
    }
  }
};
</script>
