<template>
  <div>
    <form action="" @submit.prevent="save(title, contents)">
      <input v-model.lazy="title" type="text" placeholder="Title" />
      <br />
      <br />
      <textarea v-model.lazy="contents" placeholder="Contents"></textarea>
      <hr />
      <button>저장</button>
    </form>
  </div>
</template>

<script>
import { ref, watchEffect } from 'vue';

export default {
  setup() {
    const title = ref('');
    const contents = ref('');

    const save = (title, contents) => {
      console.log(`저장되었습니다. title: ${title}, contents: ${contents}`);
    };

    watchEffect(() => {
      // 1. 최초 즉시 실행 | 2. 콜백 함수 내부의 반응형 데이터들이 변경될 경우, 실행됨
      console.log('WatchEffect');
      save(title.value, contents.value);
    });

    return { title, contents, save };
  }
};
</script>

<style lang="scss" scoped></style>
