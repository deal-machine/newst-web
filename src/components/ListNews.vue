<template>
  <div class="list">
    <div v-if="news.length > 0">
      <div v-for="(item, index) in news" :key="index">
        <div class="box">
          <NewCard :newData="item" />
        </div>
      </div>
    </div>
    <div v-else>
      <div class="box">
        <h1>There are no news to list.</h1>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import NewCard from "./NewCard.vue";
import { INew } from "@/protocols/INew";
import { defineComponent } from "vue";

const news: INew[] = [
  {
    author: "Author name",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin ornare magna eros, eu pellentesque tortor vestibulum ut. Maecenas non massa          sem. Etiam finibus odio quis feugiat facilisis.",
    title: "Title Test",
  },
  {
    author: "First author",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin magna eros, eu pellentesque tortor vestibulum ut. Maecenas non massa sem. Etiam finibus odio quis feugiat facilisis.",
    title: "Title Testing",
  },
  {
    author: "Second name",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin ornare magna eros, eu pellentesque tortor vestibulum ut. Maecenas non massa          sem. Etiam finibus odio quis feugiat facilisis.",
    title: "Title Ok",
  },
];

export default defineComponent({
  name: "ListNews",
  components: { NewCard },
  data: () => ({ news }),
});
</script>

<style scoped>
h1 {
  text-align: center;
  font-weight: 500;
}
</style>
