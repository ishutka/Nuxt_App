<template>
  <header>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">NuxtJsr</a>

        <div class="collapse navbar-collapse">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <nuxt-link
                active-class="active"
                class="nav-link active"
                aria-current="page"
                to="/"
                >Home</nuxt-link
              >
            </li>
            <li class="nav-item">
              <nuxt-link class="nav-link" no-refetch active-class="active" to="/users">
                Users
              </nuxt-link>
            </li>
            <li class="nav-item">
              <nuxt-link class="nav-link" no-refetch  active-class="active" to="/about">
                About
                </nuxt-link>
            </li>
            <li class="nav-item">
              <nuxt-link class="nav-link" no-refetch  active-class="active" to="/login">
                LogIn
                </nuxt-link>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </header>
</template>
<script>
export default {};
</script>
<style lang="scss">
.navbar-light .navbar-nav .active > .nav-link,
.navbar-light .navbar-nav .nav-link.active,
.navbar-light .navbar-nav .nav-link.show,
.navbar-light .navbar-nav .show > .nav-link {
  color: rgba(0,0,0,.5)
}
.navbar-light .navbar-nav .nav-link.nuxt-link-exact-active {
  font-weight: 500;
  color: rgba(0,0,0,.9);
}
</style>
