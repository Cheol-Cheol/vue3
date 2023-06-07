<!-- Vue3 다중 루트 노드 지원 -->
<template>
  <label class="form-label" id="child-id">
    {{ label }}
    <!-- <input v-model="value" type="text" /> -->
  </label>
  <input v-model="value" v-bind="$attrs" type="text" class="form-control" />
</template>

<script>
import { computed } from 'vue';

export default {
  props: ['modelValue', 'label'],
  emits: ['update:modelValue'],
  setup(props, { emit }) {
    const value = computed({
      get() {
        // 값을 받아올 때
        return props.modelValue;
      },
      set(value) {
        // 값이 변경될 때
        emit('update:modelValue', value);
      }
    });

    return { value };
  }
};
</script>

<style lang="scss" scoped></style>
