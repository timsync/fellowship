<template>
  <Teleport to="body">
    <Transition name="modal">
      <div  v-if="show" class="modal-mask">
        <div class="modal-container">
          <div class="modal-header">
            <slot name="header">{{ data.title }}</slot>
          </div>

          <div class="modal-body">
            <slot name="body"><div v-html="data.body"></div></slot>
          </div>

          <div class="modal-footer">
            <slot name="footer">
              {{ data.footer }}
              <button class="modal-default-button" @click="handleOk">
                好的
              </button>
            </slot>
          </div>
        </div>
      </div>
    </Transition>
  </Teleport>
</template>

<script setup lang="ts">
const props = withDefaults(
  defineProps<{
    show: boolean
    data: {
        title: string
        body: string
        footer: string
    }
  }>(),
  {
    show: false,
    data: () => ({
        title: '',
        body: '',
        footer: ''
    })
  }
);

const emit = defineEmits(['update:show', 'close'])

const handleOk = () => {
    emit("update:show", false)
}
</script>

<style scoped lang="less">
.mask {
  position: fixed;
  background-color: rgba(0, 0, 0, 0.5);
  inset: 0;
  z-index: 9999;
}

.modal-mask {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  transition: opacity 0.3s ease;
}

.modal-container {
  width: 300px;
  margin: auto;
  padding: 16px;
  background-color: #fff;
  border-radius: 2px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.33);
  transition: all 0.3s ease;
}

.modal-header {
  margin-top: 0;
  font-weight: 600;
}

.modal-body {
  margin: 10px 0;
  max-height: 60vh;
  overflow-y: scroll;
}

.modal-default-button {
  float: right;
}

/*
 * 对于 transition="modal" 的元素来说
 * 当通过 Vue.js 切换它们的可见性时
 * 以下样式会被自动应用。
 *
 * 你可以简单地通过编辑这些样式
 * 来体验该模态框的过渡效果。
 */

.modal-enter-from {
  opacity: 0;
}

.modal-leave-to {
  opacity: 0;
}

.modal-enter-from .modal-container,
.modal-leave-to .modal-container {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}
</style>
