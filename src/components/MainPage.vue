<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter" id="sidebar">
      <SideBar />
    </div>
    <div class="column is-three-quarter">
      <SearchForm @onSendSearch="handleSearch" />
      <ListNews :params="params" />
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import SideBar from "./SideBar.vue";
import ListNews from "./ListNews.vue";
import SearchForm from "./SearchForm.vue";

export default defineComponent({
  name: "MainPage",
  methods: {
    handleSearch(data: any): void {
      console.log("data: ", data);
      this.params.category = data.category;
      this.params.keywords = data.keywords;
    },
  },
  data() {
    return {
      params: {
        category: undefined,
        keywords: undefined,
      },
    };
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
