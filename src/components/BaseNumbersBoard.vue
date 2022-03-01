<template>
  <div class="w-3/5 border-4 border-black p-4">
    <ul class="list-none">
      <li v-for="number in numbers" :key="number" class="text-red-500">
        {{ number }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'BaseNumbersBoard',
  props: { numbers: Array }
}
</script>
