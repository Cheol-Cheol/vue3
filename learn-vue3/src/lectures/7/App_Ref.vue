<template>
  <div>
    <p>{{ message }}</p>
    <button @click="addMessage"></button>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const message = ref('Hello Vue!');
    const addMessage = () => {
      message.value = message.value + '!';
    };

    return { message, addMessage };
  }
};
</script>

<style lang="scss" scoped></style>
