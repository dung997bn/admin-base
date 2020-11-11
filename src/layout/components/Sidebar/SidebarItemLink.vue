<template>
  <a v-if="isExternal(to)" :href="to" target="_blank" rel="noopener">
    <slot />
  </a>
  <router-link v-else :to="to">
    <slot />
  </router-link>
</template>

<script lang="ts">
import Vue from "vue";
import { isExternal } from "@/utils/validate";
export default Vue.extend({
  name: "SidebarItemLink",
  props: {
    to: String,
  },
  data() {
    return {
      isExternal: isExternal,
    };
  },
});
</script>

<style scoped>
</style>