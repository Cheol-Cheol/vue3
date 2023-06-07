<template>
  <div></div>
</template>

<script>
import { reactive, ref, watch } from 'vue';

export default {
  setup() {
    const x = ref(0);
    const y = ref(0);

    const obj = reactive({
      count: 0
    });

    // watch(
    //   () => x.value + y.value,
    //   (sum, oldValue) => {
    //     console.log('sum: ', sum);
    //     console.log('oldValue: ', oldValue);
    //   }
    // );

    // watch([x, y], ([newX, newY]) => {
    //   console.log(newX, newY);
    // });

    // watch는 반응형 데이터를 감지한다. obj.count는 반응형이 아닌, 숫자형 데이터이기 때문에 감지하지 못한다.
    // () => obj.count 처럼 Getter 함수를 통해 접근하면 된다.
    // watch(
    //   () => obj.count,
    //   (newValue, oldValue) => {
    //     console.log('newValue: ', newValue);
    //   }
    // );

    // obj를 감지할 때는 newValue와 oldValue가 같은 객체를 가리키기 때문에 같은 값으로 출력된다.
    // watch(obj, (newValue, oldValue) => {
    //   console.log('newValue: ', newValue);
    //   console.log('oldValue: ', oldValue);
    // });

    const person = reactive({
      name: '홍길동',
      age: 30,
      hobby: '운동',
      obj: {
        count: 0
      }
    });

    watch(person, (newValue) => {
      console.log('newValue: ', newValue);
    });

    watch(
      () => person.obj,
      (newValue) => {
        console.log('newValue: ', newValue);
      }
    );

    return { x, y, obj, person };
  }
};
</script>

<style lang="scss" scoped></style>
