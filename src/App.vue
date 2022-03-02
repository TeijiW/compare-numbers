<template>
  <div class="main-container mt-12">
    <h1 class="title-1">Comparação de números</h1>
    <h2 class="title-2 mt-12">Base da comparação</h2>
    <div class="base-board mt-2">
      <IdleNumberInput
        @done="insertNumber($event)"
        placeholder="Insira um número"
        class="mb-2 border-2 text-2xl"
      />
      <BaseNumbersBoard @remove="removeNumber($event)" :numbers="numbers" />
    </div>
    <ResultAlert
      text="Número presente na lista"
      :showFlag="match"
      class="bg-green-500"
    />
    <IdleNumberInput
      @done="compareNumbers($event)"
      placeholder="Número para Comparação"
      class="mt-4 border-4 text-2xl w-1/3"
    />
  </div>
</template>

<script>
import BaseNumbersBoard from './components/BaseNumbersBoard.vue'
import IdleNumberInput from './components/IdleNumberInput.vue'
import ResultAlert from './components/ResultAlert.vue'

export default {
  name: 'App',
  components: { BaseNumbersBoard, IdleNumberInput, ResultAlert },
  data: () => {
    return { numbers: [], match: undefined }
  },
  methods: {
    insertNumber (newNumber) {
      this.numbers.push(newNumber)
    },
    removeNumber (numberToRemove) {
      this.numbers = this.numbers.filter((number) => number !== numberToRemove)
    },
    compareNumbers (numberToCompare) {
      this.match = this.numbers.includes(numberToCompare.trim())
    }
  }
}
</script>
