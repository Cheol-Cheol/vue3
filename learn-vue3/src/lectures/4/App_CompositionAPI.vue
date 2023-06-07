<template>
  <div>
    <h2>반응형 메시지</h2>
    <p>{{ resactiveMessage }}</p>
    <button v-on:click="addReactiveMessage">Add Message</button>
    <h2>일반 메시지</h2>
    <p>{{ normalMessage }}</p>
    <button v-on:click="addNomalMessage">Add Message</button>
  </div>
</template>

<script>
import { onBeforeMount, onMounted, ref } from 'vue';

export default {
  setup() {
    console.log('setup()');
    const resactiveMessage = ref('Hello Reactive Message');
    const addReactiveMessage = () => {
      resactiveMessage.value = resactiveMessage.value + '!';
    };

    let normalMessage = 'Hello Normal Message';
    const addNomalMessage = () => {
      normalMessage = normalMessage + '!';
    };

    onMounted(() => {
      console.log('onMounted');
    });

    onBeforeMount(() => {
      console.log('onBeforeMount');
    });

    return { resactiveMessage, normalMessage, addReactiveMessage, addNomalMessage };
  }
};
</script>

<style lang="scss" scoped></style>
