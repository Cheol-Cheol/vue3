<template>
  <div>
    <h2>input Value</h2>
    <!-- <input type="text" :value="inputValue" @input="(event) => (inputValue = event.target.value)" /> -->
    <input type="text" v-model.lazy="inputValue" />
    <div>{{ inputValue }}</div>

    <h2>textarea Value</h2>
    <textarea v-model="textareaValue"></textarea>
    <div>{{ textareaValue }}</div>

    <h2>checkbox Value</h2>
    <label for="checkbox">{{ checkboxValue }}</label>
    <input type="checkbox" v-model="checkboxValue" true-value="YES" false-value="NO" />

    <h3>checkbox Values</h3>
    <label>
      <input type="checkbox" value="html" v-model="checkboxValues" />
      HTML
    </label>
    <label>
      <input type="checkbox" value="css" v-model="checkboxValues" />
      CSS
    </label>
    <label>
      <input type="checkbox" value="javascript" v-model="checkboxValues" />
      JAVASCRIPT
    </label>
    <div>{{ checkboxValues }}</div>

    <h2>radio Value</h2>
    <label> <input type="radio" name="tyoe" value="O" v-model="radioValue" />O형 </label>
    <label> <input type="radio" name="tyoe" value="A" v-model="radioValue" />A형 </label>
    <div>{{ radioValue }}</div>

    <h2>select Value</h2>
    <select v-model="selectValue">
      <option value="html">HTMl 수업</option>
      <option value="css">CSS 수업</option>
      <option value="javascript">JavaScript 수업</option>
    </select>
    <div>{{ selectValue }}</div>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const inputValue = ref(null);
    const textareaValue = ref(null);
    const checkboxValue = ref('YES');
    const checkboxValues = ref([]);
    const radioValue = ref('O');
    const selectValue = ref('html');

    return { inputValue, textareaValue, checkboxValue, radioValue, selectValue, checkboxValues };
  }
};
</script>

<style lang="scss" scoped></style>
