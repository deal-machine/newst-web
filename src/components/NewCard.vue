<template>
  <article class="media">
    <figure class="media-left">
      <p class="image is-64x64">
        <img src="../assets/logo.png" alt="vue logo" />
      </p>
    </figure>
    <div class="media-content">
      <div class="content">
        <p>
          <strong>{{ newData.title }} </strong>
          <small> {{ newData.author }} </small>
          <br />
          {{ newData.description }}
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
  props: {
    newData: {
      type: Object as PropType<INew>,
      required: true,
    },
  },
});
</script>

<style scoped>
strong {
  margin-right: 6px;
}
p {
  text-align: justify;
}
</style>
