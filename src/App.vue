<template>
  <div
    v-for="(x, y, z) in object"
    :key="z"
    class="text"
    @click="addPropAndChangeColor"
  >
    {{ x }} 
  </div>
</template>

<script setup>
import { reactive, ref } from 'vue'
const object = reactive({
	firstProperty: 'This Has Color',
	SecondProperty: 'This Also Has color'
})

const color = ref('red')

const addPropAndChangeColor = function () {
	object[Math.random()] = 'Added Property does not have color'
	color.value = 'blue'
}

export {
	object,
	addPropAndChangeColor,
	color
}
</script>

<style vars="{ color }">
.text {
  color: var(--color);
}
</style>
