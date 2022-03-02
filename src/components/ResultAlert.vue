<template>
  <div
    v-show="showFlag"
    class="w-3/5 h-24 mt-4 flex justify-center items-center rounded-lg"
  >
    <span class="text-white text-4xl font-semibold">
      {{ text }}
    </span>
  </div>
</template>

<script>
export default {
  name: 'ResultAlert',
  props: { text: String, showFlag: Boolean }
}
</script>
