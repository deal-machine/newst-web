<template>
  <div class="box">
    <div class="columns">
      <div v-for="(item, index) in news" :key="index">
        <NewCard :newData="item" />
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
    description: "Description Text",
    title: "Title Test",
  },
  {
    author: "Author name",
    description: "Description Text",
    title: "Title Testing",
  },
  {
    author: "Author name",
    description: "Description Text",
    title: "Title Ok",
  },
];

export default defineComponent({
  name: "ListNews",
  components: { NewCard },

  data() {
    return { news };
  },
});
</script>
