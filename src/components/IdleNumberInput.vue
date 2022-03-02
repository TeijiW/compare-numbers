<template>
  <input
    class="p-1 border-black font-bold rounded-md"
    type="text"
    @keyup="idleTime"
    v-model="numberValue"
    :placeholder="placeholder"
  />
</template>

<script>
// ms time
const doneTimeInterval = 400

export default {
  name: 'IdleNumberInput',
  props: { placeholder: String },
  data: () => {
    return { idleTimer: undefined, numberValue: undefined }
  },
  methods: {
    idleTime (event) {
      clearTimeout(this.idleTimer)
      if (this.numberValue && this.numberValue.trim() !== '') { this.idleTimer = setTimeout(this.done, doneTimeInterval) }
    },
    done () {
      this.$emit('done', this.numberValue)
      this.numberValue = undefined
    }
  }
}
</script>
