<template>
    <div>
        <full-page ref="fullpage" :options="options" id="fullpage">
            <template v-for="(item, index) in sectionCard" :key="index">
                <home-page v-if="index === 0" id="secetion0" class="section fp-noscroll" :source="item"></home-page>
                <common-page v-else-if="index === 1" class="section fp-noscroll" :source="item">
                    <template #button>
                        <div class="more-btn">
                            <span class="btn" href="" @click="handleLearnTime">了解更多</span>
                        </div>
                    </template>
                </common-page>
                <acticve-page v-else-if="index === 2" class="section fp-noscroll"></acticve-page>
                <common-page v-else class="section fp-noscroll" :id="index === 3 ? 'secetion1' : ''" :source="item"></common-page>
            </template>
        </full-page>

        <mask-modal v-model:show="showReunionModal" :data="modalReunionData"></mask-modal>
    </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import { sectionCard, modalReunionData } from "./mock";
import commonPage from './components/common-page/index.vue'
import homePage from './components/home-page/index.vue'
import acticvePage from './components/active-page/index.vue'
import maskModal from "../home/components/mask-modal/index.vue"

const options = ref({
    licenseKey: "null",
    sectionsColor: sectionCard.map((item) => item.color), // 每个section的背景色
    // navigation: true,
    // silde
    controlArrows: false,
    // slidesNavigation: true,
    touchSensitivity: 10,
});

const showReunionModal = ref(false)
const handleLearnTime = () => {
    showReunionModal.value = true
}
</script>

<style scoped lang="less">
:deep(.section) {
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    line-height: 1;

    //   &-bg {
    //   }
    &-ct {
        padding: 0 50px;
    }

    &-title {
        font-size: 2em;
        color: #fff;
    }

    &-subTitle {
        font-size: 3em;
        font-weight: 600;
        color: #fff;
        margin-top: 10px;
    }

    &-desc {
        font-size: 1em;
        color: #fff;
        margin-top: 10px;
        font-style: italic;
    }
}

#secetion0 {
    background-image: url('@/assets/img//xk.jpeg');
    background-position: center;
    background-size: cover;
}

// 联系我们
#secetion1 {
    background-image: linear-gradient(120deg, #e0c3fc 0%, #8ec5fc 100%);
}

.more-btn {
  .btn {
    background: #245deb;
    // margin-top: 15px;
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
