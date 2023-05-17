<template>
  <form class="box">
    <div class="columns">
      <div class="column is-5">
        <div class="control">
          <input
            class="input"
            type="text"
            placeholder="Top Headlines"
            v-model="searchText"
          />
        </div>
      </div>

      <div class="column is-5">
        <div class="select">
          <select v-model="selectedItem">
            <option
              v-for="category in categories"
              :key="category"
              :value="category"
            >
              {{ category }}
            </option>
          </select>
        </div>
      </div>
      <div class="column is-1">
        <button class="button is-info" @click="onSendSearch">Search</button>
      </div>
    </div>
  </form>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "SearchForm",
  methods: {
    onSendSearch() {
      this.$emit("onSendSearch", {
        searchText: this.searchText,
        searchItem: this.selectedItem,
      });
    },
  },
  emits: ["onSendSearch"],
  data() {
    return {
      categories: [
        "",
        "business",
        "entertainment",
        "general",
        "health",
        "science",
        "sports",
        "technology",
      ],
      selectedItem: "",
      searchText: "",
    };
  },
});
</script>
