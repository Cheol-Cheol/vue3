<template>
  <div>
    <div :style="styleObject">
      Lorem, ipsum dolor sit amet consectetur adipisicing elit. Accusantium libero corporis natus
      cupiditate? Minus commodi magni, sed possimus eos cupiditate. Provident commodi quos facilis,
      iusto repellendus atque ratione minus deserunt?
    </div>
    <button @click="fontSize--">-</button>
    <button @click="fontSize++">+</button>
  </div>
</template>

<script>
import { computed, ref } from 'vue';

export default {
  setup() {
    // const styleObject = reactive({
    //   color: 'red',
    //   fontSize: '13px'
    // });

    const fontSize = ref(13);

    const styleObject = computed(() => {
      return {
        color: 'red',
        fontSize: fontSize.value + 'px'
      };
    });

    return { styleObject, fontSize };
  }
};
</script>

<style lang="scss" scoped></style>
