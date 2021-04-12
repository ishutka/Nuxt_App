<template>
<div>
  <navbar />
    <main>
      <div class="container">
        <Nuxt />
      </div>
    </main>
</div>
</template>
<script>
import Navbar from "@/components/Navbar.vue";
export default {
  name:'default',
  components: { Navbar }
};
</script>
<style></style>
