<template>
  <form @submit.prevent="onSubmit">
    <h1>Login</h1>
    <div class="form-group">
      <input type="text" class="form-control" />
    </div>
    <div class="form-group">
      <input type="text" class="form-control" />
    </div>
    <div class="bottom">
      <button type="submit" class="btn btn-primary">LogIn</button>
      <nuxt-link to="/">Home</nuxt-link>
    </div>
  </form>
</template>
<script>
export default {
  layout: "empty",
  methods:{
    onSubmit(){
      this.$store.dispatch('login');
      this.$router.push('/');
    }
  }
};
</script>
<style lang="scss" scoped>
.bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
button {
  margin-right: auto;
}
form {
  max-width: 600px;
  min-width: 300px;
}
</style>
