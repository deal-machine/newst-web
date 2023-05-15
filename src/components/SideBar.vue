<template>
  <header>
    <h1>
      <img src="../assets/logo.png" alt="Vue Logo" />
    </h1>
  </header>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "SideBar",
  props: {
    msg: String,
  },
});
</script>

<style scoped>
header {
  padding: 1rem;
  background-color: darkblue;
  width: 100%;
  height: 100vh;
}
@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}
img {
  height: 6rem;
}
</style>
