<template>
  <input
    class="p-1 border-2 border-black text-3xl font-bold"
    type="number"
    name="new-number"
    @keyup="idleTime"
    v-model="newNumber"
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
      if (this.newNumber) { this.idleTimer = setTimeout(this.done, doneTimeInterval) }
    },
    done () {
      this.$emit('done', this.newNumber)
      this.newNumber = undefined
    }
  }
}
</script>
