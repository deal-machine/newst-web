<template>
  <div class="list">
    <div v-if="isNewsExists">
      <div v-for="(item, index) in news" :key="index">
        <div v-show="item" class="box">
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
import { INew } from "@/protocols/INew";
import { httpClient } from "../http";
import NewCard from "./NewCard.vue";
import { PropType, defineComponent } from "vue";

export default defineComponent({
  name: "ListNews",
  components: { NewCard },
  data() {
    return {
      news: [] as INew[],
      isNewsExists: !!this.news,
    };
  },
  props: {
    params: {
      type: Object as PropType<{ category?: string; keywords?: string }>,
      required: true,
    },
  },
  methods: {
    post(): INew[] {
      return httpClient
        .get(
          `https://newsapi.org/v2/top-headlines?category=${this.params.category}&q=${this.params.keywords}`,
          {
            headers: {
              "X-Api-Key": "bdf1575731d84138b1fcb23e6d9a5065",
            },
          }
        )
        .then((data) => {
          return data.data.articles;
        }) as unknown as INew[];
    },
  },
  mounted() {
    const articles: INew[] = this.post();
    this.news = articles;
  },
});
</script>

<style scoped>
h1 {
  text-align: center;
  font-weight: 500;
}
</style>
