<template>
  <div class="w-3/5 border-4 border-black p-4">
    <form @submit.prevent="onSubmit">
      <input type="text" name="test" />
      <button type="submit">CLICK</button>
    </form>

    <ul class="list-none">
      <li v-for="number in numbers" :key="number" class="text-red-500">
        {{ number }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'MainContent',
  props: {},
  data: () => {
    return { numbers: [1, 2, 3, 4] }
  },
  methods: {
    onSubmit (event) {
      console.log(event)
    }
  }
}
</script>
