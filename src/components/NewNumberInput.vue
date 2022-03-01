<template>
  <input
    class="p-1 border-2 border-black text-1xl font-bold rounded-md"
    type="text"
    name="new-number"
    @keyup="idleTime"
    v-model="newNumber"
    placeholder="Insira um número"
  />
</template>

<script>
// ms time
const doneTimeInterval = 400

export default {
  name: 'NewNumberInput',
  data: () => {
    return { idleTimer: undefined, newNumber: undefined }
  },
  methods: {
    idleTime (event) {
      clearTimeout(this.idleTimer)
      if (this.newNumber && this.newNumber.trim() !== '') { this.idleTimer = setTimeout(this.done, doneTimeInterval) }
    },
    done () {
      this.$emit('done', this.newNumber)
      this.newNumber = undefined
    }
  }
}
</script>
