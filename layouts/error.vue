<template>
    <section>
        <h1>Error 404</h1>
        <p>Page not found</p>
        <nuxt-link to="/">Home</nuxt-link>
    </section>
</template>
<script>
export default {
    
}
</script>
<style lang="scss" scoped>
h1 {
    color: red;
}
section {
    display: flex;
    flex-direction: column;
    align-items: center;
}

</style>