<template>
  <div>
    <p>{{ counter }}</p>
    <p>{{ message }}</p>
    <button @click="increment">CLICK</button>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  // 컴포넌트 인스턴스가 생성(created)되기 전에 실행되는 함수(Hook) - 그래서 템플릿에 필요한 데이터들을 setup 함수 내에서 설정해서 바인딩 후 렌더링 해준 것이다.
  setup() {
    const counter = ref(0);
    const message = ref('Hello Vue3');
    const increment = () => {
      counter.value++;
    };

    return { counter, message, increment };
  }
};
</script>

<style lang="scss" scoped></style>
