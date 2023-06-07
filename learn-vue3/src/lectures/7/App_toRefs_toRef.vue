<template>
  <div>
    <p>author: {{ author }}</p>
    <p>title: {{ title }}</p>
  </div>
</template>

<script>
import { reactive, toRef } from 'vue';

export default {
  setup() {
    const book = reactive({
      author: 'Vue Team',
      year: '2020',
      title: 'Vue 3 Guide',
      description: '당신은 지금 바로 이 책을 읽습니다',
      price: '무료'
    });

    // const { author, title } = book; // 구조분해할당, 속성을 재할당 한 것이므로 반응성을 잃게 된다.
    // const { author, title } = toRefs(book); // 반응성을 유지시켜줌
    const author = toRef(book, 'author');
    const title = toRef(book, 'title');

    return { author, title, book };
  }
};
</script>

<style lang="scss" scoped></style>
