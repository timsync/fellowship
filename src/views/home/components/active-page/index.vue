<template>
  <div>
  <div class="slide active">
    <div class="slide-ct">
        <div class="active-title">活动瞬间</div>
      <div class="img-box">
        <img class="img" src="@/assets/img//img1.jpg" alt="" />
      </div>
      <div class="img-desc active-desc">左右滑动查看更多</div>
    </div>
  </div>
  <div class="slide active">
    <div class="slide-ct">
        <div class="active-title">活动瞬间</div>
      <div class="img-box">
        <img class="img" src="@/assets/img//img2.jpg" alt="" />
      </div>
      <div class="img-desc active-desc">左右滑动查看更多</div>
    </div>
  </div>
  <div class="slide active">
    <div class="slide-ct">
        <div class="active-title">活动瞬间</div>
      <div class="img-box">
        <img class="img" src="@/assets/img//img3.jpg" alt="" />
      </div>
      <div class="img-desc active-desc">左右滑动查看更多</div>
    </div>
  </div>
  <div class="slide active">
    <div class="slide-ct">
        <div class="active-title">活动瞬间</div>
      <div class="img-box">
        <img class="img" src="@/assets/img//img4.jpg" alt="" />
      </div>
      <div class="img-desc active-desc">左右滑动查看更多</div>
    </div>
  </div>
  <div class="slide active">
    <div class="slide-ct">
        <div class="active-title">活动瞬间</div>
      <div class="img-box">
        <img class="img" src="@/assets/img//img5.jpg" alt="" />
      </div>
      <div class="img-desc active-desc">左右滑动查看更多</div>
    </div>
  </div>
  <div class="slide active">
    <div class="slide-ct">
        <div class="active-title">活动瞬间</div>
      <div class="img-box">
        <img class="img" src="@/assets/img//img6.jpg" alt="" />
      </div>
      <div class="img-desc active-desc">左右滑动查看更多</div>
    </div>
  </div>
  <div class="slide active">
    <div class="slide-ct">
        <div class="active-title">活动瞬间</div>
      <div class="img-box">
        <img class="img" src="@/assets/img//img7.jpg" alt="" />
      </div>
      <div class="img-desc active-desc">左右滑动查看更多</div>
    </div>
  </div>
  </div>
</template>

<script setup lang="ts">
// import type { SectionCard } from "../../assets/types";

// const props = withDefaults(
//   defineProps<{
//     source: SectionCard;
//   }>(),
//   {
//     source: () => ({
//       title: "",
//       subTitle: "",
//       color: "",
//     }),
//   }
// );
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
