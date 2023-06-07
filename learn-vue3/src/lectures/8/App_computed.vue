<template>
  <div>
    <h2>{{ teacher.name }}</h2>
    <h3>강의가 있습니까?</h3>
    <!-- <p>{{ teacher.lectures.length > 0 ? '있음' : '없음' }}</p> -->
    <p>{{ hasLecture }}</p>
    <p>{{ hasLecture }}</p>
    <p>{{ existLecture() }}</p>
    <p>{{ existLecture() }}</p>
    <button @click="counter++">Counter: {{ counter }}</button>
    <h2>이름</h2>
    <p>{{ fullName }}</p>
  </div>
</template>

<script>
import { computed, reactive, ref } from 'vue';

export default {
  setup() {
    const teacher = reactive({
      name: '짐코딩',
      lectures: ['HTML/CSS', 'JavaScript', 'Vue3']
    });

    // 일반 메서드에 비해 성능면에서 비용이 더 적게됨 (캐시)
    const hasLecture = computed(() => {
      console.log('computed');
      return teacher.lectures.length > 0 ? '있음' : '없음';
    });

    // 컴포넌트가 업데이트 될 때 마다 계속 실행이 된다.
    const existLecture = () => {
      console.log('method');
      return teacher.lectures.length > 0 ? '있음' : '없음';
    };

    const counter = ref(0);

    const firstName = ref('홍');
    const lastName = ref('길동');

    // const fullName = computed(() => firstName.value + ' ' + lastName.value);
    const fullName = computed({
      get() {
        return firstName.value + ' ' + lastName.value;
      },
      set(value) {
        [firstName.value, lastName.value] = value.split(' ');
      }
    });
    console.log('Console 출력: ', fullName.value);

    // fullName.value = '짐 코딩'; // computed는 readonly이므로 setter를 사용할 수 없지만 다음과 같이 선언하면 가능하다.
    fullName.value = '짐 코딩';

    return { teacher, hasLecture, existLecture, counter, fullName };
  }
};
</script>

<style lang="scss" scoped></style>
