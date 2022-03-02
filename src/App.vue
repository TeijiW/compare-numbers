<template>
  <div class="main-container mt-24">
    <h1 class="title-1 mb-8">Comparação de números</h1>

    <h2 class="title-2 mb-2 mt-8">Base da comparação</h2>

    <div class="base-board">
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
