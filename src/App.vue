<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter" id="sidebar">
      <SideBar />
    </div>
    <div class="column is-three-quarter" id="list">
      <ListNews />
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import SideBar from "./components/SideBar.vue";
import ListNews from "./components/ListNews.vue";

export default defineComponent({
  name: "App",
  components: { SideBar, ListNews },
});
</script>

<style>
#sidebar {
  text-align: center;
}

#list {
  margin: 1rem;
}
</style>
