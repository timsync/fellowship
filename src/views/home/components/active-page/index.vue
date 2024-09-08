<template>
  <div>
  <div v-for="(item, index) in activePicList" class="slide active">
    <div class="slide-ct">
        <div class="active-title">{{ item.title }}</div>
      <div class="img-box">
        <img class="img" :src="item.url" alt="" />
      </div>
      <div class="img-desc active-desc">{{ item.desc }}</div>
    </div>
  </div>
  </div>
</template>

<script setup lang="ts">
import { activePicList } from './assets/index'

</script>

<style scoped lang="less">
:deep(.slide) {
  justify-content: center;
  align-items: center;
  text-align: center;
  line-height: 1;
  &-ct {
    margin: 0 auto;
    width: 80%;
    height: 100%;
    .img-box {
      border-radius: 16px;
      overflow: hidden;
      .img {
        width: 100%;
        height: 100%;
        border-radius: 16px;
      }
    }
    .img-desc {
      margin-top: 10px;
      color: #fff;
    }
  }
}

.active {
    &-title {
        font-size: 3em;
        color: #fff;
        margin-bottom: 15px;
    }
    &-desc {
        color: #f3f3f3;
    }
}
</style>
