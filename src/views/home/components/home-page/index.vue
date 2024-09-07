<template>
  <div>
      <div class="section-bg"></div>
      <div class="section-ct">
        <div class="section-title">{{ source.title }}</div>
        <div class="section-subTitle">{{ source.subTitle }}</div>
        <div class="section-desc">{{ source.desc }}</div>
        <div class="section-btn">
          <span class="btn" href="" @click="handleLearnMore">了解更多</span>
        </div>
      </div>

      <mask-modal v-model:show="showModal" :data="modalData"></mask-modal>
    </div>

</template>

<script setup lang="ts">
import { ref } from 'vue'
import type { SectionCard } from "../../assets/types";
import maskModal from "../mask-modal/index.vue"
import { modalData } from '../../mock' 

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

// const emit = defineEmits(['change', 'delete'])

const showModal = ref(false)
const handleLearnMore = () => {
    showModal.value = true
};
</script>

<style scoped lang="less">
.section-btn {
  .btn {
    background: #245deb;
    margin-top: 15px;
    color: #fff;
    border-width: 0;
    border-radius: 50px;
    padding: 0.5rem 1rem;
    font:
      1em "Margarine",
      sans-serif;
    outline: 0;
    cursor: pointer;
    position: relative;
    transition: 0.2s ease-in-out;
    letter-spacing: 2px;
    display: inline-block;
    text-decoration: none;
    line-height: 1;
  }
}
</style>
