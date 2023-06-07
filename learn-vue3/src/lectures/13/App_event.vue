<template>
  <div>
    <button @click="printEventInfo('Hello Vue3', $event)">inline event handler</button>
    <hr />
    <input type="text" @keyup="onKeyUpHandler" />
  </div>
</template>

<script>
export default {
  setup() {
    const printEventInfo = (message, event) => {
      console.log(message);
      console.log(event.target.tagName);
    };

    const onKeyUpHandler = (event) => {
      console.log(event.key);
    };

    return { printEventInfo, onKeyUpHandler };
  }
};
</script>

<style lang="scss" scoped></style>
