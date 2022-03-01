<template>
  <div class="w-full flex flex-col items-center mt-24">
    <h1 class="font-bold text-5xl mb-8">Comparação de números</h1>
    <NewNumberInput @done="insertNumber($event)" class="mb-8" />
    <BaseNumbersBoard :numbers="numbers" @remove="removeNumber($event)" />
  </div>
</template>

<script>
import BaseNumbersBoard from './components/BaseNumbersBoard.vue'
import NewNumberInput from './components/NewNumberInput.vue'

export default {
  name: 'App',
  components: { BaseNumbersBoard, NewNumberInput },
  data: () => {
    return { numbers: [] }
  },
  methods: {
    insertNumber (newNumber) {
      this.numbers.push(newNumber)
    },
    removeNumber (numberToRemove) {
      this.numbers = this.numbers.filter((number) => number !== numberToRemove)
    }
  }
}
</script>
