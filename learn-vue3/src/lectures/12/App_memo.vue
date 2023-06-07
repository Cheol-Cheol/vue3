<template>
  <!-- v-memo : subscribers만 변경 되었을 때 컴포넌트 업데이트 발생 -->
  <div v-memo="[subscribers]">
    <p>subscribers: {{ subscribers }}</p>
    <p>views: {{ views }}</p>
    <p>likes: {{ likes }}</p>
  </div>

  <button @click="subscribers++">Sub++</button>
  <button @click="views++">Views++</button>
  <button @click="likes++">Likes++</button>

  <div>
    <p>subscribers: {{ subscribers }}</p>
    <p>views: {{ views }}</p>
    <p>likes: {{ likes }}</p>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const subscribers = ref(4000);
    const views = ref(400);
    const likes = ref(20);

    return { subscribers, views, likes };
  }
};
</script>

<style lang="scss" scoped></style>
