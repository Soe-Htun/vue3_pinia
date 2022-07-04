<template>
  <div class="home">
    <!-- <div class="count">
      {{ storeCounter.count }}
    </div> -->
    <Counter/>
    <div>Double Count Computed: {{ multipleCount }}</div>

    <div class="buttons">
      <button @click="storeCounter.decreaseCount"> - </button>
      <button @click="storeCounter.increaseCount"> + </button>
      <button @click="storeCounter.waitAndAdd"> WaitAndAdd </button>
    </div>

    <hr>
    <div>
      This counter is: {{ storeCounter.oddOrEven }}
    </div>

    <hr>
    <h3>Edit counter: </h3>
    <input 
      v-model="storeCounter.count"
      type="number"
    />

  </div>
</template>

<script setup>
import { ref, computed } from "vue"
import { useCounterStore } from '@/stores/counter'
import Counter from '@/components/Counter.vue'

const storeCounter = useCounterStore()

const multipleCount = computed(() => {
  return storeCounter.count*2;
})

</script>

<style>
  .count {
    font-size: 50px;
    margin:20px;
  }
  .buttons button{
    font-size: 40px;
    margin: 10px;
  }
</style>
