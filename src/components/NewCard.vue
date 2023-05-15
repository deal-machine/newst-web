<template>
  <div class="column is-7">
    {{ newData.title }}
  </div>
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
