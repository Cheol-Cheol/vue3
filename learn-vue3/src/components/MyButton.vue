<template>
  <div class="p-3 bg-danger">
    <button class="btn btn-primary" type="button" @click="sayHello">My button</button>
    <!-- {{ $attrs }} -->
    <!-- v-bind="$attrs" 하면 원하는 노드에 non-props 속성을 바인딩 할 수 있다.-->
  </div>
</template>

<script>
export default {
  emits: ['click'],
  // inheritAttrs: false, // 루트 노드에 non-props 속성이 상속되는 것을 막을 수 있다.
  setup(props, { emit, attrs }) {
    // console.log(attrs);
    // console.log(attrs.onClick); // 이벤트는 on을 붙여서 접근해야한다.
    const sayHello = () => {
      emit('click');
    };
    return { sayHello };
  }
};
</script>

<style lang="scss" scoped></style>
