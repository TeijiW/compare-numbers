<template>
  <div class="w-full flex flex-col items-center mt-24">
    <h1 class="font-bold text-7xl mb-8">Comparação de números</h1>

    <h2 class="font-bold text-3xl text-gray-600 mb-2 mt-8">
      Base da comparação
    </h2>

    <div
      class="
        flex flex-col
        items-center
        w-3/5
        border-4
        rounded-lg
        border-black
        py-4
        px-2
      "
      style="min-height: 250px"
    >
      <NewNumberInput @done="insertNumber($event)" class="mb-2" />
      <BaseNumbersBoard :numbers="numbers" @remove="removeNumber($event)" />
    </div>
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
