<template>
  <div>
    <div class="section-bg"></div>
    <div class="section-ct">
      <div class="section-title">{{ source.title }}</div>
      <div class="section-subTitle">{{ source.subTitle }}</div>
      <div class="section-desc"><div v-html="source.desc"></div></div>
      <div class="section-btnwrap"><slot name="button"></slot></div>
    </div>
  </div>
</template>

<script setup lang="ts">
import type { SectionCard } from "../../assets/types";

const props = withDefaults(
  defineProps<{
    source: SectionCard;
  }>(),
  {
    source: () => ({
      title: "",
      subTitle: "",
      color: "",
    }),
  }
);
</script>

<style scoped lang="less">
.section-btnwrap {
    margin-top: 15px;
}
</style>
