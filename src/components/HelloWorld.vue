<template>
  <div class="hello">
    <button @click="increment">Count is: {{ count }}</button>
  </div>
</template>

<script>
const { ref, onMounted } = require('vue');
export default {
  setup() {
    const count = ref(0);
    function increment() {
      count.value++;
    }

    onMounted(() => {
      console.log(`The initial count is ${count.value}`);
    });

    return {
      count,
      increment,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
