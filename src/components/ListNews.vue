<template>
  <div class="list">
    <div v-if="isNewsExists">
      <div v-for="(item, index) in news" :key="index">
        <div v-show="item.description" class="box">
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
    url: "https://linkedin.com/in/95deal",
  },
  {
    author: "First author",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin magna eros, eu pellentesque tortor vestibulum ut. Maecenas non massa sem. Etiam finibus odio quis feugiat facilisis.",
    title: "Title Testing",
    publishedAt: "2023-05-16T12:11:00Z",
  },
  {
    author: "Second name",
    url: "https://linkedin.com/in/95deal",
    publishedAt: "2023-05-16T12:11:00Z",

    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin ornare magna eros, eu pellentesque tortor vestibulum ut. Maecenas non massa          sem. Etiam finibus odio quis feugiat facilisis.",
    title: "Title Ok",
  },
];

export default defineComponent({
  name: "ListNews",
  components: { NewCard },
  data: () => ({ news, isNewsExists: news.length > 0 }),
});
</script>

<style scoped>
h1 {
  text-align: center;
  font-weight: 500;
}
</style>
