<template>
  <article class="media">
    <figure class="media-left">
      <p class="image is-64x64">
        <img src="../assets/logo.png" alt="vue logo" />
      </p>
    </figure>
    <div class="media-content">
      <div class="content">
        <p v-show="newData.description">
          <strong v-show="newData.title">{{ newData.title }} </strong>
          <small v-show="newData.author"> {{ newData.author }} </small>
          <br />
          {{ newData.description }}
          <br />
          <small v-show="newData.url">
            <a target="_blank" :href="newData.url">Visit</a>
          </small>
          <small v-show="newData.publishedAt">
            {{ newData.publishedAt }}
          </small>
        </p>
      </div>
    </div>
  </article>
</template>

<script lang="ts">
import { PropType, defineComponent } from "vue";
import { INew } from "@/protocols/INew";
export default defineComponent({
  name: "NewCard",
  data() {
    return {
      pageName: "",
    };
  },
  props: {
    newData: {
      type: Object as PropType<INew>,
      required: true,
    },
  },
});
</script>

<style scoped>
strong,
small {
  margin-right: 1rem;
}
p {
  text-align: justify;
}
</style>
