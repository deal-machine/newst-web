<template>
  <form class="box">
    <div class="columns">
      <div class="column is-4">
        <div class="control">
          <input
            class="input"
            type="text"
            placeholder="Top Headlines"
            v-model="searchText"
          />
        </div>
      </div>

      <div class="column is-4">
        <div class="select">
          <select v-model="selectedItem">
            <option v-for="item in items" :key="item" :value="item">
              {{ item }}
            </option>
          </select>
        </div>
      </div>
      <div class="column is-2">
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
      items: [
        "ae",
        "ar",
        "at",
        "au",
        "be",
        "bg",
        "br",
        "ca",
        "ch",
        "cn",
        "co",
        "cu",
        "cz",
        "de",
        "eg",
        "fr",
        "gb",
        "gr",
        "hk",
        "hu",
        "id",
        "ie",
        "il",
        "in",
        "it",
        "jp",
        "kr",
        "lt",
        "lv",
        "ma",
        "mx",
        "my",
        "ng",
        "nl",
        "no",
        "nz",
        "ph",
        "pl",
        "pt",
        "ro",
        "rs",
        "ru",
        "sa",
        "se",
        "sg",
        "si",
        "sk",
        "th",
        "tr",
        "tw",
        "ua",
        "us",
        "ve",
        "za",
      ],
      selectedItem: "pt",
      searchText: "",
    };
  },
});
</script>
