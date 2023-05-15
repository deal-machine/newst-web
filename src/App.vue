<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter" id="sidebar">
      <SideBar />
    </div>
    <div class="column is-three-quarter">
      <SearchForm @onSendSearch="handleSearch" />
      <ListNews />
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import SideBar from "./components/SideBar.vue";
import ListNews from "./components/ListNews.vue";
import SearchForm from "./components/SearchForm.vue";

export default defineComponent({
  name: "App",
  methods: {
    handleSearch(data: any): void {
      console.log(data);
    },
  },
  components: { SideBar, ListNews, SearchForm },
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
