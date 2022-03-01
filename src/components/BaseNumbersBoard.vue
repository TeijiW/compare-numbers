<template>
  <ul class="list-none inline p-0">
    <li class="inline" v-for="number in numbers" :key="number">
      <button
        class="
          bg-gray-200
          text-gray-700
          border-gray-600 border-2
          rounded-xl
          py-1
          px-2
          hover:bg-red-300 hover:text-red-700 hover:border-red-600
          font-bold
          text-xl
        "
        @click="remove"
      >
        {{ number }}
      </button>
    </li>
  </ul>
</template>

<style>
li::after {
  content: " ";
}
li:last-child::after {
  content: "";
}
</style>

<script>
export default {
  name: 'BaseNumbersBoard',
  props: { numbers: Array },
  methods: {
    remove (event) {
      const number = event.target.textContent
      this.$emit('remove', number)
    }
  }
}
</script>
