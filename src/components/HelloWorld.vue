<template>
  <div class="hello">
    <button @click="increment">Count is: {{ count }}</button>
    <ul>
      <li v-for="item in state.arr">{{item}}</li>
    </ul>
    <p>{{state.msg}}</p
  </div>
</template>

<script>
import { ref, onMounted, reactive } from 'vue';
export default {
  setup() {
    const count = ref(0);
    const state = reactive({
      arr: [1],
    });

    function increment() {
      count.value++;
      state.arr[2] = 3
      state.msg = '3'

      // console.log(state instanceof Proxy)
    }

    onMounted(() => {
      console.log(`The initial count is ${count.value}`);
    });

    onMounted(() => {
      console.log(`The initial count is ${count.value}131`);
    });

    return {
      count,
      increment,
      state
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
